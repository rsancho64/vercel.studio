# Vercel Explicado

*brave-search:*
`que es vercel y para que se usa`

- **Vercel** es una plataforma de desarrollo y hosting en nube. Se especializa en **crear, desplegar y escalar web apps**
- desplegar y escalar aplicaciones web modernas de manera:
  - rápida y eficiente (desarrolladores!)
  - segura (empresas!)
- piensa especialmente en frameworks js: Next.js, React, Vue.js y otros. 
- Fundada en 2015; ha evolucionado y es una suite de herramientas que simplifican el ciclo de vida del desarrollo web.

**Características clave de Vercel:**

1. Vercel permite desplegar webapps directamente desde repos Git (GitHub, GitLab o Bitbucket, ..) sin configurar servidores o infraestructura manualmente.
2. **Optimización automática** de imágenes, código y otros recursos desde la plataforma: ++rendimiento y velocidad de carga de las apps.
3. Vercel admite funciones sin servidor (serverless) para manejar solicitudes API, autenticación y otros procesos backend.
4. La plataforma se integra fácilmente con repositorios de Git: despliegues automatizados y controlado de versiones.
5. **CDN**: distribuye las apps a través de su CDN -*red de entrega de contenido*- global: ++velocidad y rendimiento -en cualquier dispositivo-.
6. **Seguridad**: habilita HTTPS y ofrece configuración de encabezados HTTP: proteger los datos de los usuarios.
7. Escalado automatico a demanda: no configurar servidores adicionales.

¿sitios web estáticos o prototipos de aplicaciones? Proyectos personales!

por todo: **simplifica el ciclo de vida** -del desarrollo web- *automatizando*:
    automatizando fases despliegue, optimización, 
    preintegrando componentes: serverless functions y seguridad
.. ideal para desarrolladores web y empresas que buscan crear aplicaciones web modernas y escalables.

## MEW w python (?)

[un MEW](https://dev.to/andrewbaisden/how-to-deploy-a-python-flask-app-to-vercel-2o5k) con posibilidades y que refiere a [este otro](https://github.com/headwinds/venv).

## MEW w js

*brave-search:*
`Vercel with javascritp Tutorial`

Vercel with JavaScript Tutorial

Vercel is a platform that enables you to build, deploy, and manage modern web applications with ease. In this tutorial, we'll explore how to use Vercel with JavaScript to deploy a Next.js application.

**Prerequisites**

- [x] Node.js installed on your machine
- [x] A Vercel account
- [x] Familiarity with JavaScript and Next.js

**Step 1: Create a New Next.js Project**

Run the following command to create a new Next.js project:

```bash:
npx create-next-app@latest --typescript
```

This will create a new directory with a basic Next.js project structure.

**Step 2: Configure Vercel**

In your project directory, create a new file named `vercel.json` with the following content:

```json:
{
  "version": 2,
  "rewrites": [
    {
      "source": "/(.*)",
      "destination": "/api/$1"
    }
  ]
}
```

This configuration tells Vercel to route all incoming requests to the `/api` folder.

**Step 3: Deploy to Vercel**

Run the following command to deploy your project to Vercel:
```bash
vercel
```
This will upload your project to Vercel, build it, and deploy it. You'll receive a URL for your application.

**Step 4: Test Your Deployment**

Open your browser and navigate to the URL provided by Vercel. You should see your Next.js application running.

**Additional Tips**

* Use the `vercel env` command to pull the latest environment variables for your project.
* Use the `vercel --dev` command to run your function locally.
* Choose a runtime for your function (e.g., Node.js or Edge) by exporting a `runtime` property in your `vercel.json` file.
* Learn more about Vercel Functions and how to use them in your application.

**Resources**

* Vercel Documentation: [Getting Started with Vercel](https://vercel.com/docs/getting-started)
* Next.js Documentation: [Getting Started with Next.js](https://nextjs.org/docs/getting-started)
* Vercel Functions Documentation: [Functions API Reference](https://vercel.com/docs/functions/api-reference)

**Conclusion**

In this tutorial, we've covered the basics of deploying a Next.js application to Vercel using JavaScript. With Vercel, you can easily manage and scale your web applications, and with Next.js, you can build fast and efficient server-side rendered applications. By combining these two technologies, you can create a powerful and scalable web development stack.
