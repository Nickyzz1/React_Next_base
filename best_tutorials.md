# Fonte com NEXT & Tailwind

1. importe a fonte no seu arquivo layout.tsx

   `import { Outfit } from 'next/font/google'`
    
    `const outfit = Outfit({
      subsets: ['latin'],
      weight: ['400', '600', '700'],
      variable: '--font-outfit',    // para usar como CSS var
    })`

2. atualize no tailwind.config.js:

    `module.exports = {
    content: ['./app/**/*.{js,ts,jsx,tsx}'],
    theme: {
      extend: {
        fontFamily: {
          outfit: ['var(--font-outfit)', 'sans-serif'],
        },
      },
    },
    }`

Agora já é possível usar assim:

    <p className="font-outfit text-lg">
      Este parágrafo está usando a fonte Outfit!
    </p>

# Modo escuro

- No seu arquivo tailwind.config.js, ative o modo escuro:

   `module.exports = {
     darkMode: 'class', // 👈 usamos a classe 'dark' para ativar
     content: [
       './app/**/*.{js,ts,jsx,tsx}',
       './pages/**/*.{js,ts,jsx,tsx}',
       './components/**/*.{js,ts,jsx,tsx}',
     ],
     theme: {
       extend: {},
     },
     plugins: [],
   }`

2. Use classes dark: nos seus estilos Tailwind

  <div className="bg-white text-black dark:bg-zinc-900 dark:text-white min-h-screen p-4">
     <h1 className="text-3xl font-bold">Olá, Nini!</h1>
     <p>Esse texto muda de cor no modo escuro!</p>
   </div>`





