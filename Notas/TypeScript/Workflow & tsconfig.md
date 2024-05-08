Inicializando o arquivo de configurações:

```
tsc --init
```

#### Propriedades importantes:
**Language and Environment**
- "target": "es2016" # ESNext para usar a última versão do ECMAScript.

**Modules**
- "rootDir": "./"  # Local onde ficarão os arquivos TS.

**Emit**
- "outDir": "./" # Local onde ficarão os arquivos JS compilados.

Após a propriedade *compilerOptions*:
"include": ["src"] # Impede que arquivos sejam compilados fora da pasta root.
