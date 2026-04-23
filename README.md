# 🌿 EcoMonitor - Painel de Sustentabilidade

O **EcoMonitor** é uma aplicação desenvolvida em Blazor que permite monitorar ações sustentáveis, como reciclagem de plástico, descarte de eletrônicos e plantio de árvores, recompensando o usuário com pontos e "broches" visuais em um quadro dinâmico.

---

## 👤 Identificação
* **Nome Completo:** Arthur Kyldare
* **Curso:** Cienca da Computaçao

---

## 🧠 Heurísticas de Nielsen Aplicadas
Neste projeto, foram aplicadas as seguintes diretrizes de usabilidade:

1.  **Visibilidade do Status do Sistema:** O componente mantém o usuário informado sobre o que está acontecendo em tempo real. Ao clicar em "Registrar", o contador de pontos é atualizado instantaneamente e um ícone (broche) surge no Quadro Branco, confirmando que a ação foi processada com sucesso.
2.  **Reconhecimento em vez de Recordação:** O sistema utiliza ícones visuais (🥤, 💻, 🌳) e rótulos claros nos cards. Isso reduz a carga cognitiva do usuário, que não precisa memorizar quais ações geram quais pontos, pois as informações estão sempre visíveis e organizadas.

---

## 🚀 Guia de Execução
Para rodar este projeto localmente, siga os passos abaixo:

1.  **Certifique-se de ter o SDK do .NET instalado** (Versão 8.0 ou superior).
2.  Abra o terminal na pasta raiz do projeto.
3.  Execute o comando para restaurar as dependências e rodar a aplicação:
    ```bash
    dotnet watch run
    ```
4.  O terminal indicará uma URL (ex: `https://localhost:5001`). Copie e cole no seu navegador.

---

## 🛠️ Explicação Técnica: Uso de [Parameter]
Para tornar os componentes do EcoMonitor reutilizáveis e modulares, utilizamos o atributo `[Parameter]`. 

**Como funciona:**
Em vez de criar três códigos diferentes para os cards (Plástico, Eletrônico e Árvore), podemos criar um único componente chamado `EcoCard.razor`. Através do `[Parameter]`, passamos informações diferentes para cada instância, como:
* **Título** da atividade.
* **Valor** dos pontos.
* **Ícone** correspondente.

Exemplo de uso no código:
```razor
// Dentro do componente reutilizável
[Parameter] public string Titulo { get; set; }
[Parameter] public int Pontos { get; set; }

// Chamada na página principal
<EcoCard Titulo="Plantio de Árvores" Pontos="10" />
