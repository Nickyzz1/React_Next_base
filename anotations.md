# declarations.d.ts

--> quando você usa SVG precisa desse arquivo. Nesse file, você está ensinando o TypeScript a entender arquivos que ele, por padrão, não reconhece como código TypeScript.

Por que o nome é declarations.d.ts?
O sufixo .d.ts significa: definition file (arquivo de definição de tipos).

É uma convenção comum chamar esse arquivo de declarations.d.ts, mas você pode dar outro nome, tipo:

  - svg.d.ts
  
  - custom-modules.d.ts
  
  - types/global.d.ts

Contanto que ele esteja incluído nos caminhos de TypeScript (tsconfig.json) e tenha o sufixo .d.ts.

# include

  `{
    "include": ["next-env.d.ts", "**/*.ts", "**/*.tsx", "**/*.d.ts"]
  }`

💬 Isso significa:
“Ei, TypeScript! Analisa e entende todos os arquivos que terminem com .ts, .tsx e .d.ts em qualquer pasta, além do next-env.d.ts.”

# Net.config.ts

✅ O que é:
Arquivo de configuração principal do Next.js.

📄 Coisas que você configura aqui:

 - Redirecionamentos (redirects)
  
 - Rewrites de rota (rewrites)
  
 - Configurações do Webpack (ex: suportar .svg)
  
 - Variáveis de ambiente públicas
  
 - Internacionalização (i18n)
  
 - Output (export, standalone, etc.)

🌍 Internacionalização (i18n)
Configura o app para lidar com vários idiomas.

ts

    i18n: {
      locales: ['pt-BR', 'en'],
      defaultLocale: 'pt-BR',
    }

🌱 Variáveis de ambiente públicas
Você pode definir variáveis de ambiente públicas, que começam com NEXT_PUBLIC_.

Exemplo:

  env
  `NEXT_PUBLIC_API_URL=https://api.meusite.com`
  ts
  `process.env.NEXT_PUBLIC_API_URL`


☘️Restringir origens:

      reactStrictMode: true,
      images: {
        domains: ['meusite.com'],
      },
  
🔄 Rewrites de rota (rewrites)
Permite que uma URL pareça uma coisa, mas internamente aponte para outra.
Diferente do redirect, aqui a URL do navegador não muda.

    async rewrites() {
      return [
        {
          source: '/api/produtos',
          destination: 'https://api.minhaempresa.com/produtos',
        },
      ];
    }




