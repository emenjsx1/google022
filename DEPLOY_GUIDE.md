# 🚀 Guia de Deploy no Netlify

## ✅ Problema Resolvido!

O erro "Page not found" acontecia porque o Netlify procura por `index.html` na raiz do projeto, mas você tinha `version.html`.

## 📋 Arquivos Criados para Resolver:

1. ✅ **index.html** - Cópia do version.html (arquivo principal)
2. ✅ **netlify.toml** - Configuração do Netlify
3. ✅ **_redirects** - Redirecionamentos (backup)
4. ✅ **.gitignore** - Ignora arquivos desnecessários

## 🔄 Como Fazer o Deploy Novamente:

### Opção 1: Deploy via Drag & Drop (Mais Fácil)

1. Acesse: https://app.netlify.com/drop
2. Arraste TODA a pasta `OFERTA GOOGKE` para a área de drop
3. Aguarde o upload completar
4. Pronto! Seu site estará no ar

### Opção 2: Deploy via Netlify CLI

```bash
# Instalar Netlify CLI (se ainda não tiver)
npm install -g netlify-cli

# Fazer login
netlify login

# Deploy
cd "c:\Users\PRECISION\Downloads\OFERTA GOOGKE"
netlify deploy --prod
```

### Opção 3: Deploy via Git/GitHub

1. Crie um repositório no GitHub
2. Faça push dos arquivos
3. Conecte o repositório ao Netlify
4. Deploy automático!

## 📁 Estrutura Correta para Deploy:

```
OFERTA GOOGKE/
├── index.html          ← ARQUIVO PRINCIPAL (obrigatório)
├── version.html        ← Mantido para compatibilidade
├── netlify.toml        ← Configuração do Netlify
├── _redirects          ← Redirecionamentos
├── css2                ← Estilos
├── scripts/            ← JavaScript
├── lib/                ← Bibliotecas
└── [outras pastas]     ← Recursos do site
```

## ⚙️ O que o netlify.toml faz:

- Define a pasta de publicação como raiz (`.`)
- Redireciona `/version.html` para `/index.html`
- Redireciona todas as rotas para `index.html` (SPA behavior)
- Define headers de segurança
- Configura Content-Type correto para arquivos

## 🔍 Verificações Antes do Deploy:

✅ Arquivo `index.html` existe na raiz  
✅ Arquivo `netlify.toml` existe na raiz  
✅ Todas as pastas de recursos estão incluídas  
✅ Não há arquivos `.py` sendo enviados (opcional)  

## 🌐 Após o Deploy:

Seu site estará acessível em:
- `https://seu-site.netlify.app/`
- `https://seu-site.netlify.app/version.html` (também funciona)

## 🐛 Troubleshooting:

### Se ainda der erro 404:
1. Verifique se `index.html` está na raiz
2. Limpe o cache do Netlify: Site Settings → Build & Deploy → Clear cache
3. Faça um novo deploy

### Se os recursos não carregarem:
1. Verifique se todas as pastas foram enviadas
2. Confira os caminhos no HTML (devem ser relativos)
3. Veja o console do navegador para erros

### Se o vídeo não funcionar:
- Alguns recursos de vídeo dependem de CDNs externas
- Verifique se os arquivos `.m3u8` foram enviados
- Pode ser necessário configurar CORS

## 📞 Suporte:

Se precisar de ajuda:
1. Verifique os logs de deploy no Netlify
2. Acesse: Site → Deploys → [último deploy] → Deploy log
3. Procure por erros em vermelho

---

**Agora é só fazer o upload novamente! 🎉**
