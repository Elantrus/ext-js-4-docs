# ExtJS 4 Documentation Extractor

Este projeto extrai a documentação do ExtJS 4 a partir da API oficial da Sencha e converte para formato Markdown.

## Funcionalidades

✅ **Extração completa da documentação** incluindo:
- Informações básicas da classe (extends, aliases, etc.)
- Descrição principal da classe
- Exemplos de código
- Configurações (Config options)
- Propriedades (Properties)
- Métodos (Methods)
- Eventos (Events)
- Variáveis CSS (CSS Variables)
- Mixins CSS (CSS Mixins)

✅ **Conversão automática para Markdown** com formatação adequada

✅ **Suporte a qualquer classe do ExtJS 4**

## Requisitos

- Node.js (versão 14 ou superior)
- Bun (opcional, mas recomendado)
- curl (para download dos dados)

## Instalação

1. Clone ou baixe este repositório
2. Instale as dependências (se necessário):

```bash
npm install
# ou
bun install
```

## Uso

### Script Genérico

Para extrair documentação de qualquer classe do ExtJS 4:

```bash
node extract_extjs_docs.js <NomeDaClasse>
```

**Exemplos:**

```bash
# Extrair documentação do Panel
node extract_extjs_docs.js Ext.panel.Panel

# Extrair documentação do Grid
node extract_extjs_docs.js Ext.grid.Panel

# Extrair documentação do Button
node extract_extjs_docs.js Ext.button.Button

# Extrair documentação do Form
node extract_extjs_docs.js Ext.form.Panel
```

### Script Específico (Panel)

Para usar o script específico do Panel:

```bash
node index.js
```

## Estrutura dos Arquivos Gerados

Para cada classe extraída, são gerados os seguintes arquivos:

- `<NomeDaClasse>.md` - Documentação em Markdown
- `<NomeDaClasse>_data.json` - Dados JSON extraídos da API
- `<NomeDaClasse>_raw.js` - Arquivo JSONP original baixado

## Exemplo de Saída

```
✅ Documentação gerada em: Ext.panel.Panel.md
📊 Seções encontradas: Config options, Properties, Methods, Events, CSS Variables, CSS Mixins
💡 Exemplos de código: 3
   Config options: 714 itens
   Properties: 593 itens
   Methods: 536 itens
   Events: 102 itens
   CSS Variables: 57 itens
   CSS Mixins: 1 itens
```

## Estrutura da Documentação Markdown

A documentação gerada segue esta estrutura:

```markdown
# Nome.da.Classe

**Extends:** ClassePai
**Widget Alias:** alias
**Alternate Names:** nomes alternativos

## Descrição
Descrição principal da classe...

## Exemplos
### Exemplo 1
```javascript
// Código de exemplo
```

## Config options
### nomeConfig
**Tipo:** TipoDoConfig
Descrição da configuração...

## Properties
### nomePropriedade
**Tipo:** TipoDaPropriedade
Descrição da propriedade...

## Methods
### nomeMetodo
Descrição do método...

## Events
### nomeEvento
Descrição do evento...

## CSS Variables
### $variavel-css
Descrição da variável CSS...

## CSS Mixins
### nome-mixin
Descrição do mixin CSS...
```

## Como Funciona

1. **Download**: O script baixa os dados da API oficial do ExtJS 4 via JSONP
2. **Parsing**: Extrai o JSON do formato JSONP
3. **Processamento**: Analisa o HTML da documentação e extrai as seções
4. **Conversão**: Converte para Markdown com formatação adequada
5. **Geração**: Salva o arquivo Markdown final

## API do ExtJS 4

O script utiliza a API oficial da Sencha:

```
https://cdn.sencha.com/ext/gpl/4.2.1/docs/output/{ClassName}.js?callback=Ext.data.JsonP.{ClassName}&_dc={timestamp}
```

## Limitações

- Funciona apenas com ExtJS 4.2.1
- Requer conexão com a internet para baixar os dados
- Algumas formatações complexas podem não ser preservadas perfeitamente

## Contribuição

Sinta-se à vontade para contribuir com melhorias:

1. Fork o projeto
2. Crie uma branch para sua feature
3. Commit suas mudanças
4. Push para a branch
5. Abra um Pull Request

## Licença

MIT License

## Classes Populares do ExtJS 4

Algumas classes úteis para extrair documentação:

- `Ext.panel.Panel` - Painel básico
- `Ext.grid.Panel` - Grid/Tabela
- `Ext.form.Panel` - Formulário
- `Ext.button.Button` - Botão
- `Ext.window.Window` - Janela
- `Ext.tree.Panel` - Árvore
- `Ext.tab.Panel` - Abas
- `Ext.toolbar.Toolbar` - Barra de ferramentas
- `Ext.menu.Menu` - Menu
- `Ext.container.Container` - Container
- `Ext.Component` - Componente base
- `Ext.data.Store` - Store de dados
- `Ext.data.Model` - Modelo de dados
