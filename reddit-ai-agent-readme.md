# Reddit AI Agent

Agente de IA que realiza scraping de Reddit para generar ideas de nuevos agentes basados en las discusiones de la comunidad.

## Descripción

Este proyecto implementa un agente de IA que:
- Realiza scraping de foros específicos de Reddit
- Utiliza LibreTranslate como modelo de traducción automatizada
- Analiza el contenido para generar ideas innovadoras de agentes de IA

## Modelo de Traducción

LibreTranslate ha sido seleccionado como el modelo de traducción por:
- Código abierto y gratuito
- Implementación sencilla
- Ejecución local o mediante API
- Soporte para múltiples idiomas
- Sin límites de uso en modo local

## Requisitos Previos

- Python 3.8+
- Cuenta de Reddit con API credentials
- LibreTranslate (local o API)
- Modelo de IA para análisis y generación de ideas

## Instalación

```bash
git clone https://github.com/usuario/reddit-ai-agent
cd reddit-ai-agent
pip install -r requirements.txt
pip install libretranslate
```

## Configuración

1. Crea un archivo `.env` en el directorio raíz:

```env
REDDIT_CLIENT_ID=tu_client_id
REDDIT_CLIENT_SECRET=tu_client_secret
REDDIT_USER_AGENT=nombre_de_tu_aplicacion
REDDIT_SUBREDDIT=artificial
LIBRETRANSLATE_URL=https://translate.argosopentech.com  # Opcional: URL de API pública
```

2. Configura las credenciales de la API de Reddit en [Reddit Developer Portal](https://www.reddit.com/prefs/apps)

## Implementación de LibreTranslate

```python
from libretranslate import LibreTranslate

class Translator:
    def __init__(self):
        self.lt = LibreTranslate()
    
    def translate_text(self, text: str, source_lang: str = "en", target_lang: str = "es") -> str:
        """
        Traduce texto usando LibreTranslate
        
        Args:
            text (str): Texto a traducir
            source_lang (str): Idioma origen (default: "en")
            target_lang (str): Idioma destino (default: "es")
            
        Returns:
            str: Texto traducido
        """
        return self.lt.translate(text, source_lang, target_lang)
```

## Estructura del Proyecto

```
reddit-ai-agent/
├── src/
│   ├── scraper.py      # Módulo de scraping
│   ├── translator.py    # Módulo de traducción con LibreTranslate
│   └── analyzer.py      # Módulo de análisis y generación
├── tests/
├── .env
├── requirements.txt
└── README.md
```

## Funcionalidades

- **Scraping**: Extrae posts y comentarios del subreddit configurado
- **Traducción**: Convierte contenido usando LibreTranslate
- **Análisis**: Genera ideas de agentes basadas en las discusiones
- **Exportación**: Guarda resultados en formato estructurado

## Contribución

1. Fork el repositorio
2. Crea una rama (`git checkout -b feature/nueva-funcionalidad`)
3. Commit los cambios (`git commit -am 'Agrega nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Crea un Pull Request

## Licencia

MIT License
