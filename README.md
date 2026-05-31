# 🔗 VMF - Markdown Link Validator

[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](LICENSE)
![Language: JavaScript](https://img.shields.io/badge/Language-JavaScript-yellow.svg)
![Status: Active Development](https://img.shields.io/badge/Status-Active%20Development-brightgreen.svg)

> **VMF** é uma ferramenta CLI robusta para validar e analisar links em arquivos Markdown.

---

## 📋 Sobre

VMF (Validador de Markdown Files) é uma CLI que:
- ✅ **Extrai** todos os links presentes em arquivos Markdown
- 🔍 **Valida** cada link via requisições HTTP
- 📊 **Retorna** status code e mensagem de status para cada URL
- 🎯 **Oferece** 3 modos de operação flexíveis

Perfeito para verificar links quebrados em documentações, projetos ou qualquer arquivo Markdown!

---

## 🚀 Instalação

### Global (Recomendado)
```bash
npm install -g vmf
```

### Local
```bash
npm install vmf
```

---

## 💻 Como Usar

### 1️⃣ Modo Padrão (Diretório `./files/`)
Valida todos os arquivos Markdown na pasta padrão:
```bash
vmf
```

### 2️⃣ Modo Diretório Customizado
Valida todos os arquivos de um diretório específico:
```bash
vmf --rootdir /caminho/para/seu/diretorio
```

**Exemplo:**
```bash
vmf --rootdir ./docs
vmf --rootdir ./src/docs
```

### 3️⃣ Modo Arquivo Específico
Valida apenas um arquivo Markdown:
```bash
vmf --filepath /caminho/para/arquivo.md
```

**Exemplo:**
```bash
vmf --filepath ./README.md
vmf --filepath ./docs/tutorial.md
```

---

## 📤 Output

O VMF retorna um array com todos os links validados:

```json
[
  {
    "Link Text": "https://example.com",
    "status": 200,
    "statusText": "OK"
  },
  {
    "Documentation": "https://docs.example.com",
    "status": 404,
    "statusText": "Not Found"
  }
]
```

**Campos retornados:**
- `Link Text`: Texto do link encontrado no Markdown
- `URL`: A URL completa
- `status`: Código HTTP de resposta
- `statusText`: Descrição do status

---

## 🛠️ Tecnologias

- **Node.js** - Runtime JavaScript
- **node-fetch** - Validação HTTP de URLs
- **chalk** - Styling de output no terminal
- **Jest** - Framework de testes

---

## 📦 Dependências

```json
{
  "chalk": "^4.1.2",      // Colorização de output
  "node-fetch": "^2.6.7"  // Requisições HTTP
}
```

---

## 🧪 Testes

Execute a suite de testes com:
```bash
npm test
```

---

## 📁 Estrutura do Projeto

```
vmf/
├── cli.js                      # Entry point da CLI
├── package.json                # Configuração e dependências
├── README.md                   # Este arquivo
├── src/
│   ├── execute-cli.js         # Lógica principal da CLI
│   ├── extract-files-links.js # Extração de links em arquivos
│   ├── extract-dir-links.js   # Leitura de diretórios
│   ├── http-validation.js     # Validação HTTP de URLs
│   └── valid-arguments.js     # Validação de argumentos CLI
└── test/
    └── test.js                # Testes automatizados
```

---

## ⚙️ API

### `extractLinks(markdown)`
Extrai todos os links em formato `[text](url)` de um texto Markdown.

### `validateLinks(urlArray)`
Valida um array de URLs e retorna status HTTP para cada uma.

### `readFile(filePath)`
Lê um arquivo Markdown e retorna seus links validados.

### `readDirectory(dirPath)`
Lê todos os arquivos Markdown em um diretório e retorna links validados.

---

## 🐛 Tratamento de Erros

VMF fornece mensagens de erro claras:

```bash
# Arquivo não encontrado
vmf --filepath ./inexistente.md
# ❌ Error: File Not Found

# Diretório não encontrado
vmf --rootdir ./docs-inexistentes
# ❌ Error: Directory Not Found

# Argumentos inválidos
vmf --invalid-arg
# ❌ Error: Invalid argument
```

---

## 💡 Casos de Uso

- 🔗 Verificar links quebrados em documentações
- 📚 Validar repositórios inteiros de documentos
- 🤖 Integrar em pipelines CI/CD
- 📊 Auditar saúde de links em projetos

---

## 👤 Autor

**Kauan Amorim**
- Email: kauanamorim88@gmail.com
- LinkedIn: [Kauan Amorim](https://www.linkedin.com/in/kauan-amorim-a1035213b/)
- GitHub: [@KauanAmorim](https://github.com/KauanAmorim)

---

## 📄 Licença

Este projeto está licenciado sob a **ISC License** - veja os detalhes em [LICENSE](LICENSE)

---

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para:
1. Fork o projeto
2. Criar uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abrir um Pull Request

---

## 🔄 Roadmap

- [ ] Suporte para mais formatos de link
- [ ] Relatórios em JSON e CSV
- [ ] Configuração de timeout customizável
- [ ] Integração com GitHub Actions
- [ ] Dashboard web para visualização
- [ ] Cache de validações

---

## 📞 Suporte

Encontrou um problema? Abra uma [issue](https://github.com/KauanAmorim/vmf/issues) ou entre em contato via email.

---

## ⭐ Se gostou, deixe uma star! 

**Feito com ❤️ por Kauan Amorim**