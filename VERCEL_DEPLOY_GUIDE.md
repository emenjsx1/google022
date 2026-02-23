# 🚀 Guia de Deploy no Vercel

## ✅ Problema Resolvido!

O erro 404 no Vercel foi resolvido com a criação do arquivo `vercel.json`.

## 📋 Arquivos Criados:

1. ✅ **vercel.json** - Configuração do Vercel com rotas e redirecionamentos
2. ✅ **index.html** - Página principal (já existia)

## 🔄 Como Fazer o Deploy no Vercel:

### Opção 1: Deploy via GitHub (Recomendado)

1. **Primeiro, faça push do vercel.json:**
   ```bash
   git add vercel.json
   git commit -m "Add Vercel configuration"
   git push origin main
   ```

2. **Conecte ao Vercel:**
   - Acesse: https://vercel.com/new
   - Clique em "Import Git Repository"
   - Selecione: **emenjsx1/google022**
   - Configure:
     - **Framework Preset**: Other
     - **Root Directory**: `./`
     - **Build Command**: (deixe vazio)
     - **Output Directory**: `./`
   - Clique em "Deploy"

3. **Aguarde o deploy** ✨

### Opção 2: Deploy via Vercel CLI

```bash
# Instalar Vercel CLI
npm install -g vercel

# Fazer login
vercel login

# Deploy
cd "c:\Users\PRECISION\Downloads\OFERTA GOOGKE"
vercel --prod
```

### Opção 3: Deploy via Drag & Drop

1. Acesse: https://vercel.com/new
2. Clique em "Deploy"
3. Arraste a pasta `OFERTA GOOGKE`
4. Aguarde o upload

## ⚙️ O que o vercel.json faz:

```json
{
  "routes": [
    "/version.html → /index.html",  // Redireciona version.html
    "/* → /index.html"               // Fallback para SPA
  ],
  "headers": [
    "Security headers",              // Proteção XSS, etc
    "CORS para .m3u8"                // Suporte a vídeo streaming
  ]
}
```

## 📁 Estrutura para Vercel:

```
OFERTA GOOGKE/
├── index.html          ← ARQUIVO PRINCIPAL
├── vercel.json         ← CONFIGURAÇÃO DO VERCEL ⭐
├── version.html        ← Compatibilidade
├── css2                ← Estilos
├── scripts/            ← JavaScript
├── lib/                ← Bibliotecas
└── [outras pastas]     ← Recursos
```

## 🔍 Diferenças Vercel vs Netlify:

| Recurso | Vercel | Netlify |
|---------|--------|---------|
| Config  | `vercel.json` | `netlify.toml` |
| Rotas   | JSON routes | `_redirects` |
| Build   | Automático | Automático |
| CDN     | Global | Global |

## 🐛 Troubleshooting:

### Se ainda der erro 404:

1. **Verifique se `vercel.json` está na raiz**
   ```bash
   ls vercel.json  # Deve existir
   ```

2. **Limpe o cache e redeploy:**
   - Vercel Dashboard → Settings → General
   - Scroll até "Deployment Protection"
   - Clique em "Redeploy"

3. **Verifique os logs:**
   - Vercel Dashboard → Deployments
   - Clique no último deploy
   - Veja "Build Logs" e "Function Logs"

### Se os recursos não carregarem:

1. **Verifique os caminhos no HTML:**
   - Devem ser relativos (sem `/` no início)
   - Exemplo: `scripts/utms/latest.js` ✅
   - Não: `/scripts/utms/latest.js` ❌

2. **Verifique se todas as pastas foram enviadas:**
   ```bash
   git status
   git add .
   git commit -m "Add missing files"
   git push
   ```

### Se o vídeo não funcionar:

- Arquivos `.m3u8` precisam de CORS (já configurado no vercel.json)
- Verifique se os arquivos de vídeo foram enviados
- Alguns vídeos dependem de CDNs externas

## 📊 Verificação Pós-Deploy:

✅ Site carrega em `https://seu-projeto.vercel.app`  
✅ `/version.html` redireciona para `/index.html`  
✅ Recursos CSS/JS carregam corretamente  
✅ Vídeos funcionam (se aplicável)  
✅ Sem erros no console do navegador  

## 🌐 URLs que devem funcionar:

- `https://seu-projeto.vercel.app/` ✅
- `https://seu-projeto.vercel.app/index.html` ✅
- `https://seu-projeto.vercel.app/version.html` ✅

## 🔗 Links Úteis:

- **Vercel Dashboard**: https://vercel.com/dashboard
- **Documentação**: https://vercel.com/docs
- **Seu Repositório**: https://github.com/emenjsx1/google022

---

**Agora faça o push do vercel.json e redeploy! 🎉**
