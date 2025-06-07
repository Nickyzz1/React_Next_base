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
