# Cyber Sphere Tech — Next.js 15 Portfolio

Responsive futuristic portfolio for Shubham Sapkal using Next.js 15, React 19, TypeScript, Three.js, React Three Fiber, Drei, Framer Motion, and Lucide icons.

## Included
- Procedural interactive 3D wireframe sphere, particle connections, orbital rings, stars and sparkles
- Animated hero, scroll reveal transitions, responsive sticky navigation and mobile menu
- Dark/light theme toggle and active section indicator
- Sections: Home, About, Skills, Experience, Projects, Home Lab, Certifications, Blog, Contact
- SEO metadata, robots.txt, Netlify configuration and environment variable example
- No public Proxmox/Docker API calls and no secrets required

## Requirements
Node.js 20+ and npm.

## Run locally
```bash
npm install
cp .env.example .env.local
npm run dev
```
Open http://localhost:3000. Test production build with `npm run build`.

## Customize before launch
1. Set `NEXT_PUBLIC_CONTACT_EMAIL` in `.env.local` and Netlify environment variables. It is public by design and should only contain your contact email.
2. Add a real resume at `public/resume.pdf`, then update the current Download Resume link in `components/Portfolio.tsx` to `/resume.pdf`. The current button opens an email request because no resume file was supplied.
3. Verify experience, project summaries, statistics and certification claims; replace placeholders with accurate details.
4. Confirm GitHub and LinkedIn URLs in `components/Portfolio.tsx`.
5. Add project repository links if available.

## Deploy to Netlify
1. Push the project to a Git repository.
2. In Netlify, choose **Add new site → Import an existing project** and connect the repository.
3. Use build command `npm run build`; `netlify.toml` configures the Next.js plugin and Node 20.
4. Add `NEXT_PUBLIC_CONTACT_EMAIL` under Site configuration → Environment variables if desired.
5. Deploy and inspect the build log.

Netlify CLI alternative:
```bash
npm install
npm install -g netlify-cli
netlify login
netlify init
netlify deploy --build --prod
```

## Security checklist
- Never put API keys, tokens, private keys or credentials in `NEXT_PUBLIC_*` variables; those values are shipped to browsers.
- `.env.local` is ignored by Git. Do not commit secrets.
- This frontend does not connect to your Proxmox, Docker or other management APIs. Keep administration interfaces behind private access and never expose management APIs directly to the internet.
- If adding a form provider later, use a server-side route, server-only environment variables, input validation, spam protection and rate limiting.
- Use HTTPS and keep dependencies patched. Review `npm audit` before production deployment.

## Notes
The sphere is generated using Three.js geometry rather than a static image. Portfolio content and statistics are starter content and should be verified before publication. The 3D scene animates independently; CSS and Framer Motion honor reduced-motion preferences.
