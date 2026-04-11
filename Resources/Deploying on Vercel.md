# 🚀 The Complete Guide to Deploying on Vercel (Beginner → Intermediate)

## 📖 Introduction

**Vercel** is a cloud platform for static sites and Serverless Functions that makes deployment instant and painless. It integrates directly with Git (GitHub, GitLab, Bitbucket) and automatically builds & deploys your code on every `git push`.

Why developers love Vercel:
- ✅ Zero-config deployment for Next.js, React, Vue, and more  
- ✅ Automatic HTTPS + custom domains  
- ✅ Environment variables management  
- ✅ Global CDN + edge network  
- ✅ Free tier for personal projects  

---

## 🧒 Method 1: Simple Deployment (Beginner Friendly)

Perfect for static sites, SPAs, or full-stack Next.js apps where frontend and backend live together.

### 1️⃣ Connect your GitHub repository
- Push your code to a GitHub repo (public or private)  
- Go to [vercel.com](https://vercel.com) → **Add New Project**  
- Import your GitHub repository  
- Vercel automatically detects the framework (React, Vue, etc.)

### 2️⃣ Add environment variables (if needed)
- In the Vercel project dashboard → **Settings** → **Environment Variables**  
- Add keys like:  
  ```
  NEXT_PUBLIC_API_URL = https://your-api.com
  DATABASE_URL    = your_database_connection
  ```
- **Important:** Variables starting with `NEXT_PUBLIC_` are exposed to the browser. Keep secrets server-side only.

### 3️⃣ Click deploy
- Hit **Deploy** → Vercel builds and deploys in seconds  
- Get your live URL: `https://your-project.vercel.app`  
- Every future `git push` to the main branch auto-deploys 🔄

---

## 🔧 Method 2: Deploy Client & Server Separately (Intermediate)

When you have a separate backend (Node.js, Python, Go) and frontend (React, Vue, Svelte). Both can live on Vercel.

### Step-by-step:

#### 1️⃣ Deploy the backend/server first
- Push backend code to a GitHub repo  
- Import into Vercel (make sure it has a `vercel.json` or proper build settings)  
- **Example `vercel.json` for Node.js backend:**
  ```json
  {
    "functions": { "api/*.js": { "runtime": "nodejs18.x" } }
  }
  ```

#### 2️⃣ Add all required environment variables to backend
- Go to backend’s Vercel dashboard → **Settings** → **Environment Variables**  
- Add `DATABASE_URL`, `SECRET_KEY`, `STRIPE_KEY`, etc.  
- These never reach the frontend – safe and secure 🔒

#### 3️⃣ Get the deployed backend URL
- After deployment, Vercel gives a URL like:  
  `https://your-backend.vercel.app`  
- Copy this – you’ll need it for the frontend.

#### 4️⃣ Use backend URL in frontend environment variables
- In your frontend project, create a variable pointing to the backend:  
  ```
  VITE_API_URL = https://your-backend.vercel.app/api
  ```
  (or `REACT_APP_API_URL` for Create React App, `NEXT_PUBLIC_API_URL` for Next.js)

#### 5️⃣ Deploy the frontend/client
- Push frontend code to GitHub  
- Import into Vercel (new project)  
- Add the same `VITE_API_URL` variable in frontend’s environment settings  
- Click **Deploy**

#### 6️⃣ ✅ Both frontend and backend are live and connected
- Test a login or data fetch – they should talk to each other seamlessly.

---

## 🧪 Testing Your Deployment

### Test backend APIs using Postman
- Open Postman → New request  
- Hit your backend URL + endpoint:  
  `https://your-backend.vercel.app/api/health`  
- Expect `200 OK` or actual JSON response  
- If you get `404` or `500`, check logs in Vercel dashboard → **Functions** tab.

### Verify frontend is calling backend correctly
- Open your live frontend URL: `https://your-frontend.vercel.app`  
- Open browser **Developer Tools** → **Network** tab  
- Perform an action that calls the API (login, fetch data)  
- Look for requests to your backend URL – status should be `200` or `201`  
- If you see `CORS` errors or `Failed to fetch`, check the next section 👇

---

## ⚠️ Common Mistakes to Avoid

| Mistake | Why it hurts | Fix |
|---------|--------------|-----|
| ❌ Missing environment variables | Backend or frontend fails silently | Double-check Vercel dashboard → Environment Variables |
| ❌ Wrong API URL in frontend | Frontend calls `localhost:3000` in production | Use `VITE_API_URL` + redeploy frontend |
| ❌ CORS issues | Browser blocks requests from frontend to backend | Add CORS headers in backend: `res.setHeader('Access-Control-Allow-Origin', '*')` (for dev) |
| ❌ Forgetting to redeploy after changes | Code change is in GitHub but not live | Every push to main branch triggers deploy – but if you change env vars, you must redeploy manually |
| ❌ Exposing secrets in frontend | API keys visible in browser console | Never put secrets in `NEXT_PUBLIC_*` or `VITE_*` variables |

---

## 💡 Pro Tips (From Real Experience)

- 🧩 **Use `.env` files locally** – Vercel’s CLI can push them: `vercel env pull`  
- 🔄 **Keep backend & frontend separate** – Easier to scale, debug, and redeploy independently  
- 🧪 **Test APIs first** – Use Postman or `curl` before connecting frontend. Half the debugging time disappears.  
- 📁 **Use `vercel.json`** – Define routes, rewrites, and serverless function configs explicitly  
- 👀 **Monitor deployments** – Vercel gives a unique preview URL for every PR. Share it with your team instantly.  
- 🔁 **Redeploy after env var changes** – Environment variables are not hot-reloaded. Go to Deployments → click three dots → **Redeploy**.

---

## 🎯 Conclusion

You don’t need a DevOps degree to ship full‑stack projects anymore.  

- Start with **Method 1** for simple apps or Next.js.  
- Move to **Method 2** when your backend and frontend grow apart.  
- Test everything, avoid common traps, and use pro tips to save hours.  

Vercel removes the pain of servers, SSH, and configs – so you can focus on **building**.  

Now go deploy something awesome 🚀  
And remember: every expert was once a beginner who didn’t give up.  

**Happy shipping!** 🎉

## 🤝 Contributing

Found an amazing resource? Want to add your favorite course? Check out our [CONTRIBUTING.md](../CONTRIBUTING.md) to learn how you can help grow this collection!

## 🔗 Connect With Me

[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/parth.builds)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/parthnarkar)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/parthnarkar)
[![LeetCode Profile](https://img.shields.io/badge/LeetCode-ParthNarkar-FFA116?style=for-the-badge&logo=leetcode)](https://leetcode.com/u/parthnarkar/)
[![Email](https://img.shields.io/badge/-Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:parthnarkarofficial@gmail.com)
[![Twitter](https://img.shields.io/badge/-Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/parthnarkar)
[![Discord](https://img.shields.io/badge/-Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/users/parth_narkar)

### ⭐ Found this helpful? Give this Repo a STAR!

[![parth-builds-os Github Repo Footer](https://github.com/user-attachments/assets/4bef3a04-16ee-4484-a52c-4f31182e1916)](https://github.com/parthnarkar/parth-builds-os)
