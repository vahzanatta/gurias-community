# Gurias Community

Landing page da **Gurias Community** — um espaço para conectar mulheres com conexões reais, liberdade de participação e eventos mensais em Porto Alegre e região.

🌐 **Site:** [vahzanatta.github.io/gurias-community](https://vahzanatta.github.io/gurias-community/)

---

## Sobre o projeto

Site institucional da comunidade com as seções:

- **Sobre** — o que é a comunidade e suas atividades mensais
- **Como funciona** — taxa mensal e passo a passo para entrar
- **Eventos passados** — registro dos encontros realizados
- **Agenda** — próximos eventos
- **Instagram** — feed integrado via [Behold.so](https://behold.so) *(ativar com Widget ID)*
- **Sugestões** — formulário de feedback
- **Inscrição** — formulário de cadastro para novas membras

## Stack atual

- HTML5 + CSS3 + JavaScript vanilla
- Design responsivo (mobile-first + desktop)
- Deploy automático via GitHub Actions → GitHub Pages

## Próximos passos

- [ ] Migração para **Vue.js**
- [ ] Integração real do feed do Instagram (Behold.so)
- [ ] Backend para recebimento dos formulários

## Ativar feed do Instagram

1. Crie uma conta gratuita em [behold.so](https://behold.so)
2. Conecte o Instagram `@guriascommunity`
3. Crie um widget e copie o **Widget ID**
4. No `index.html`, localize a variável e cole o ID:

```js
const BEHOLD_ID = 'SEU_WIDGET_ID_AQUI';
```

## Deploy

O deploy é automático a cada push na branch `main` via GitHub Actions.

Para subir manualmente:

```bash
git add .
git commit -m "sua mensagem"
git push origin main
```
