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

1.No seu arquivo tailwind.config.js, ative o modo escuro:

      module.exports = {
        darkMode: 'class', // 👈 usamos a classe 'dark' para ativar
        content: [
          './app/**/*.{js,ts,jsx,tsx}',
          './pages/**/*.{js,ts,jsx,tsx}',
          './components/**/*.{js,ts,jsx,tsx}',
        ],
        theme: {
          extend: {
           colors: {
           background: {
             DEFAULT: '#ffffff',       // cor clara padrão
             dark: '#121212',          // cor escura padrão
           },
           text: {
             DEFAULT: '#111111',       // texto claro padrão
             dark: '#e5e5e5',          // texto escuro padrão
           },
           // Pode adicionar outras cores personalizadas aqui
          },
        },
        plugins: [],
      }

2.Use classes dark: nos seus estilos Tailwind
      
      <div className="bg-white text-black dark:bg-zinc-900 dark:text-white min-h-screen p-4">
        <h1 className="text-3xl font-bold">Olá, Nini!</h1>
        <p>Esse texto muda de cor no modo escuro!</p>
      </div>`
2.1.Para usar as variáveis de cores:

      <div className="bg-background text-text dark:bg-background-dark dark:text-text-dark min-h-screen p-4">
        <h1 className="text-3xl font-bold">Olá, Nini!</h1>
        <p>Esse texto muda de cor no modo escuro!</p>
      </div>

# Modo escuro com mui/material

1.Crie um arquivo Theme.ts com usuas paletas

      // theme.ts
      import { createTheme } from '@mui/material/styles'
      
      export const darkTheme = createTheme({
        palette: {
          mode: 'dark', // ativa o modo escuro
        },
      })
      
      export const lightTheme = createTheme({
        palette: {
          mode: 'light',
        },
      })


2.Agora para alterar entre eles você deve usar o themeprovaider

   <pre> ```// pages/_app.tsx ou app/layout.tsx (com client component)
      import { useState } from 'react'
      import { ThemeProvider } from '@mui/material/styles'
      import CssBaseline from '@mui/material/CssBaseline'
      import { lightTheme, darkTheme } from '@/theme' 
      
      export default function MyApp({ Component, pageProps }) {
        const [darkMode, setDarkMode] = useState(false)
      
        const toggleDarkMode = () => setDarkMode(!darkMode)
      
        return (
          <ThemeProvider theme={darkMode ? darkTheme : lightTheme}>
            <CssBaseline /> {/* Normaliza estilos base do MUI */}
            <button onClick={toggleDarkMode} style={{margin: 16}}>
              {darkMode ? 'Modo Claro' : 'Modo Escuro'}
            </button>
            <Component {...pageProps} />
          </ThemeProvider>
        )
      } ``` <pre/>




