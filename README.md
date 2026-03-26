# Math Tutor API Proxy

Secure Vercel serverless function to proxy NVIDIA API requests for Mickey's Math Tutor.

## Security

✅ **NO API keys in code or Git history**  
✅ API key stored securely in Vercel Environment Variables  
✅ CORS enabled for GitHub Pages frontend  

## Setup

### 1. Deploy to Vercel

Click: [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/Annaxiebot/math-api-proxy)

### 2. Add Environment Variable

After deployment:
1. Go to Vercel Dashboard → Your Project → Settings
2. Click **Environment Variables**
3. Add:
   - **Key:** `NVIDIA_API_KEY`
   - **Value:** Your NVIDIA API key from https://build.nvidia.com/
   - **Environments:** Production, Preview, Development (all 3)
4. Save

### 3. Redeploy

After adding the environment variable, redeploy to activate it.

## Usage

**Endpoint:** `POST /api`

**Example:**
```javascript
fetch('https://your-project.vercel.app/api', {
  method: 'POST',
  headers: {'Content-Type': 'application/json'},
  body: JSON.stringify({
    model: 'meta/llama-3.1-8b-instruct',
    messages: [{role: 'user', content: 'Give me 3 slope problems'}],
    max_tokens: 1024,
    temperature: 0.7
  })
})
```

## License

MIT
