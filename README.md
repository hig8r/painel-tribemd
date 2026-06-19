# Painel de Escala — TribeMD

Painel web para controle de dias presenciais e home office da equipe.
Substitui o controle por planilha Excel por uma interface única, com:

- Escala fixa de mesas por dia (segunda a sexta), replicada da planilha original
- Visão automática de quem está em home office em cada dia
- Filtro por cargo (Coordenador, Dados, Front-end, Fullstack, Mobile, QA, UX/UI)
- Resumo semanal por pessoa
- Estatísticas do dia selecionado

O projeto é uma página estática (HTML/CSS/JS em um único arquivo), sem dependências
e sem build. Basta hospedar o `index.html`.

## Estrutura

```
painel-tribemd/
├── index.html   (o painel completo)
├── README.md
└── .gitignore
```

## Como publicar no GitHub Pages

1. Crie um repositório novo no GitHub (ex.: `painel-escala`).
2. Suba o conteúdo desta pasta para o repositório (os arquivos devem ficar
   na raiz do repositório, não dentro de uma subpasta).
3. No repositório, vá em **Settings > Pages**.
4. Em **Source**, selecione a branch `main` e a pasta `/ (root)`.
5. Salve. Em alguns instantes o GitHub gera a URL pública, no formato:
   `https://SEU-USUARIO.github.io/painel-escala/`

Essa URL é o link de acesso ao painel.

## Como subir pelo terminal

```bash
cd painel-tribemd
git init
git add .
git commit -m "Painel de escala TribeMD"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/painel-escala.git
git push -u origin main
```

Depois ative o Pages conforme os passos acima.

## Como editar a escala ou os cargos

Tudo fica no `index.html`, dentro da tag `<script>`:

- **Escala de mesas:** objeto `ESCALA`. Cada dia é uma lista de nomes na ordem
  das mesas (a posição na lista define o número da mesa).
- **Cargos:** objeto `CARGO`. Para mudar o cargo de alguém, edite o valor
  correspondente ao nome.

Após editar, basta fazer um novo commit e push; o GitHub Pages atualiza sozinho.
