[Back to Home](../../README.md) / [1.5 Software Guidelines](1.5-software_guidelines.md) / **Visual Studio Code Setup**

<hr>

### Recommended Settings:

Copy this into your `settings.json` inside the `.vscode` folder.

```json
{
    "telemetry.enableTelemetry": false,
    "telemetry.telemetryLevel": "off",
    "editor.formatOnSave": true,
    "python.analysis.indexing": true,
    "python.formatting.provider": "autopep8",
    "python.formatting.autopep8Args": [
        "--max-line-length",
        "120"
    ],
}
```
In case you prefer black formatter over autopep8 change this setting in the block above and use these formatting arguments:
```json
    "python.formatting.blackArgs": [
        "--line-length",
        "120"
    ],
```
Once you have the Autodocstring Extension installed use these settings:
```json
    "autoDocstring.docstringFormat": "numpy",
    "autoDocstring.startOnNewLine": true,
```