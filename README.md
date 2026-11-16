# PRTS · mapas e mods

Catálogo oficial de mapas e mods do PRTS. O launcher do jogo lê o `index.toml` deste repositório, mostra as prévias e instala com um clique. Cada arquivo é conferido pelo sha256 antes de ser instalado.

## Estrutura

```
index.toml                 # catálogo (gerado, não edite os hashes à mão)
maps/<id>/map.toml         # nome, autor, versão, bases e jazidas
maps/<id>/height.png       # relevo, (cells+1)×(cells+1) em tons de cinza
maps/<id>/preview.png      # prévia mostrada no launcher
```

O nome da pasta `<id>` precisa ser igual ao `id` do `map.toml` e usar só letras minúsculas, números, `-` e `_`. Pacotes não podem conter código executável.

## Adicionar ou atualizar um mapa

1. Crie ou edite a pasta em `maps/<id>/`. Para mudar um mapa já publicado, aumente o `version` no `map.toml`.
2. Gere o índice com o jogo (Godot 4.7.2, projeto do PRTS):
   ```
   "<Godot 4.7.2>" --path <PRTS>/godot --headless -- --build-index=<caminho deste repositório>
   ```
3. Faça commit e push dos mapas junto com o `index.toml`.

O `.gitattributes` mantém os bytes dos arquivos intactos, para os hashes do índice continuarem valendo.
