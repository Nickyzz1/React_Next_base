# declarations.d.ts

--> quando você usa SVG precisa desse arquivo. Nesse file, você está ensinando o TypeScript a entender arquivos que ele, por padrão, não reconhece como código TypeScript.

Por que o nome é declarations.d.ts?
O sufixo .d.ts significa: definition file (arquivo de definição de tipos).

É uma convenção comum chamar esse arquivo de declarations.d.ts, mas você pode dar outro nome, tipo:

svg.d.ts

custom-modules.d.ts

types/global.d.ts

Contanto que:

Ele esteja incluído nos caminhos de TypeScript (tsconfig.json).

E tenha o sufixo .d.ts.

# include

  {
    "include": ["next-env.d.ts", "**/*.ts", "**/*.tsx", "**/*.d.ts"]
  }

💬 Isso significa:
“Ei, TypeScript! Analisa e entende todos os arquivos que terminem com .ts, .tsx e .d.ts em qualquer pasta, além do next-env.d.ts.”
