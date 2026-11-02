# PDFKit Local

**Ferramentas PDF gratuitas, privadas e simples de usar.**
*Free, private PDF tools that run entirely in your browser.*

Junte PDFs, extraia páginas e gire documentos direto no navegador. Os arquivos **não são enviados a nenhum servidor**: a leitura e o processamento acontecem no seu dispositivo.

## O problema

Muitas ferramentas de PDF impõem limites, exigem cadastro, exibem marcas d’água ou pedem o envio de documentos que podem conter informações privadas. O PDFKit Local oferece as operações essenciais em uma interface direta, com processamento local.

## Funcionalidades

| Funcionalidade | Descrição | Estado |
| --- | --- | --- |
| Juntar PDFs | Combina vários arquivos em um único PDF, na ordem escolhida (com botões para reordenar). | Implementado |
| Extrair páginas | Cria um PDF com páginas ou intervalos informados, como `1-3, 5`. | Implementado |
| Girar páginas | Rotação de 90°, 180° ou 270° nas páginas escolhidas (vazio = todas). | Implementado |
| Adicionar arquivos | Seleção de arquivos e área de arrastar e soltar. | Implementado |
| Comprimir PDF | Reduzir o tamanho do documento com opções de qualidade. | Planejado |
| Imagens para PDF | Converter imagens em um documento PDF. | Planejado |

## Público-alvo

Estudantes, profissionais administrativos, pequenos negócios, professores, freelancers e qualquer pessoa que precise organizar PDFs sem instalar um programa dedicado.

## Stack

- **TypeScript**: lógica da aplicação com tipagem estática
- **Vite**: servidor de desenvolvimento e build otimizado
- **pdf-lib**: leitura, cópia, criação e manipulação de páginas PDF
- **HTML/CSS**: interface responsiva, sem framework visual

Modelo: aplicação client-side, sem backend.

## Como executar

Requisitos: **Node.js 18 ou superior**. Na pasta do projeto:

```bash
npm install
npm run dev       # desenvolvimento em http://localhost:5173
```

Para validar a versão de produção:

```bash
npm run build     # verifica os tipos e gera a pasta dist/
npm run preview
```

## Como usar

1. Escolha a ferramenta na aba: **Juntar PDFs**, **Extrair páginas** ou **Girar páginas**.
2. Arraste os PDFs para a área indicada ou clique para selecioná-los.
3. Em **Juntar**, ajuste a ordem com os botões ↑ e ↓.
4. Em **Extrair** e **Girar**, informe as páginas, por exemplo `1-3, 5`. Em **Girar**, deixar em branco gira todas.
5. Clique no botão de ação. O PDF resultante é baixado automaticamente.

## Estrutura do projeto

```
pdfkit-local/
├── index.html        # página inicial e interface
├── src/
│   ├── main.ts       # interações da interface
│   ├── pdf.ts        # operações com PDF: juntar, extrair, girar e intervalos
│   └── style.css     # estilos
├── vite.config.ts
├── tsconfig.json
├── LICENSE
└── README.md
```

A lógica de PDF fica isolada em `src/pdf.ts`, o que facilita testes e a adição de novas ferramentas.

## Publicação no GitHub

1. Crie um repositório público chamado `pdfkit-local`, adicione os arquivos e publique este README.
2. Para uma demonstração online, rode `npm run build` e publique a pasta `dist/` em GitHub Pages, Netlify, Cloudflare Pages ou similar. O `base` do Vite já é relativo.
3. Descrição sugerida: `Free, private PDF tools that run entirely in your browser.`
4. Tópicos sugeridos: `pdf-tools` `merge-pdf` `split-pdf` `pdf-editor` `privacy-first` `open-source` `browser-tools`

## Privacidade e segurança

- O MVP **não implementa upload** dos documentos: os arquivos são lidos pelo navegador e processados localmente.
- Essa promessa deve ser preservada em futuras versões.
- Se forem adicionadas métricas, elas não devem coletar nomes, conteúdo ou dados sensíveis dos documentos.
- Não prometemos anonimato absoluto nem segurança perfeita.
- PDFs protegidos por senha não são suportados.

## Roadmap

- [x] Permitir reordenar arquivos antes de juntar
- [ ] Adicionar compressão de PDF, explicando os limites técnicos
- [ ] Converter imagens para PDF
- [ ] Exibir miniaturas e permitir seleção visual de páginas
- [ ] Adicionar testes automatizados para intervalos de páginas
- [ ] Configurar integração contínua para validar o build
- [ ] Publicar demonstração online e documentação em inglês

## Como contribuir

Contribuições são bem-vindas:

1. Abra uma issue para discutir a ideia ou o problema.
2. Crie um branch a partir do principal.
3. Garanta que `npm run build` passa sem erros.
4. Envie um pull request descrevendo a mudança.

Mantenha o princípio central: **nenhum arquivo do usuário sai do navegador**.

## Como medir o sucesso

Acompanhe indicadores verificáveis: visitantes que concluem uma operação, taxa de erro no processamento, tempo para concluir tarefas, issues resolvidas e contribuições externas. Estrelas no GitHub indicam interesse, mas não substituem uso real e feedback.

## Licença

Distribuído sob a licença [MIT](LICENSE).
