# Física • Abel Coelho — PWA

Portal educacional de Física desenvolvido como projeto independente para a comunidade da **Escola Estadual Professor Abel Freire Coelho**. O site não é um canal institucional oficial.

## O que funciona

- Interface responsiva, para computador e celular.
- **18 aulas** em 6 trilhas (Cinemática, Dinâmica, Energia, Ondulatória, Eletricidade e Gravitação).
- **3 desafios**, com 4 perguntas cada, explicações e pontuação recorde.
- **Laboratório de lançamento oblíquo** com velocidade, ângulo e gravidade da Lua, Terra ou Júpiter; gráfico animado e cálculos.
- **19 fórmulas** com busca e filtro por assunto.
- Progresso e pontuações guardados **no próprio navegador** via `localStorage` (sem servidor/banco de dados).
- PWA instalável, com `manifest.webmanifest`, ícones, `service worker` e suporte a **uso offline após o primeiro carregamento**.
- Sem bibliotecas, conta, banco de dados ou API externa — somente HTML, CSS e JavaScript.

## Publicar e instalar no celular

**Importante:** PWA precisa ser hospedado em **HTTPS** ou em `localhost`. Abrir o arquivo `index.html` diretamente (`file://`) não habilita a instalação/offline.

### Opção 1: Netlify Drop (mais fácil)

1. Acesse https://app.netlify.com/drop e faça login, se necessário.
2. Arraste a pasta `abel-coelho-fisica-pwa` inteira (descompactada) para a área de publicação.
3. Abra o endereço HTTPS disponibilizado pelo Netlify no celular.
4. **Android com Chrome:** use o botão **Instalar app** no site ou o menu `⋮` > **Instalar app / Adicionar à tela inicial**.
5. **iPhone com Safari:** toque em **Compartilhar** > **Adicionar à Tela de Início**.

### Opção 2: GitHub Pages (grátis)

1. Crie um repositório no GitHub, por exemplo `fisica-abel-coelho`.
2. Faça upload de **todos os arquivos e da pasta `icons`** na raiz do repositório (não apenas do ZIP).
3. Vá a **Settings > Pages > Build and deployment > Deploy from a branch**.
4. Escolha a branch `main` e pasta `/(root)`, depois **Save**.
5. Abra o endereço `https://SEU_USUARIO.github.io/fisica-abel-coelho/` no celular e instale o PWA.

Os caminhos do PWA são relativos: ele funciona tanto no domínio raiz quanto em um subdiretório do GitHub Pages.

### Testar localmente

Com Python instalado, entre na pasta do projeto e rode:

```bash
python -m http.server 8000
```

Abra http://localhost:8000 no navegador. Para testar a instalação no telefone, publique em HTTPS.

## Onde editar

- `index.html`: layout e conteúdo base.
- `styles.css`: aparência e responsividade.
- `app.js`: aulas, exercícios, fórmulas, simulação e lógica da interface.
- `manifest.webmanifest`: título, ícones e modo de abertura do PWA.
- `sw.js`: cache offline. **Após publicar uma atualização**, aumente o número em `CACHE_NAME` (ex.: `v1` → `v2`) para atualizar o conteúdo armazenado nos dispositivos.
- `icons/`: ícones PNG usados pelo Android, iPhone e navegador.

## Limitações intencionais

Sem backend, o progresso não sincroniza entre dispositivos. Ao limpar os dados do navegador, o progresso local pode ser apagado. O laboratório usa equações idealizadas (sem resistência do ar e com mesma altura de partida e chegada), o que é explicado na interface.

Projeto demonstrativo educacional. Não há autenticação, publicação de notas oficiais nem vínculo oficial com a direção escolar.
