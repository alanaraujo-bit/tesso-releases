# TESSO — instaladores assinados

Este repositório público hospeda **somente** os instaladores do TESSO para Windows, já assinados, e o manifesto do atualizador. O código-fonte do TESSO é privado e **não** fica aqui.

- **Download:** <https://github.com/alanaraujo-bit/tesso-releases/releases/latest>
- **Manifesto do atualizador (Tauri):** `https://github.com/alanaraujo-bit/tesso-releases/releases/latest/download/latest.json`

Cada release traz três arquivos:
- `TESSO_<versão>_x64-setup.exe`: o instalador NSIS;
- `TESSO_<versão>_x64-setup.exe.sig`: a assinatura minisign do Tauri, verificada pelo app antes de instalar uma atualização;
- `latest.json`: o manifesto.

## Como os releases chegam aqui
1. O pipeline do repositório privado compila e assina o instalador.
2. Ele envia os três arquivos para um branch `incoming/v<versão>` deste repositório, usando uma deploy key só para isso.
3. O workflow `publish.yml` transforma esse branch num GitHub Release e apaga o branch.
