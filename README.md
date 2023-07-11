# Projeto de Estacionamento com TypeScript

Um dos projetos mais desafiadores até o momento, porém consegui concluí-lo e além disso exercitar muitas coisas que já aprendi em JavaScript até aqui
Foram muitas horas produtivas, o resultado valeu super a pena!

Apesar do tempo que levei é uma aplicação simples que permite cadastrar veículos em um estacionamento virtual. Ele foi desenvolvido utilizando as seguintes tecnologias:

- HTML
- CSS
- JavaScript
- TypeScript


### Funcionalidades

O projeto possui as seguintes funcionalidades:

1. Cadastro de veículos: Permite cadastrar um veículo informando seu nome e placa.
2. Listagem de veículos: Exibe a lista de veículos cadastrados no estacionamento, mostrando seu nome, placa e horário de entrada.
3. Remoção de veículos: Permite remover um veículo do estacionamento.

## Principais funções 

- Função `calcTempo`: Calcula o tempo decorrido com base em milissegundos e retorna uma string formatada com o tempo em minutos e segundos.
Exemplo:

```
    const tempo = calcTempo(120000);
    console.log(tempo); // Output: "2m e 0s"


```

- Função `patio`: Contém todas as funcionalidades relacionadas ao estacionamento, como ler, salvar, adicionar, remover e renderizar os veículos.

```
    const estacionamento = patio();
    estacionamento.adicionar({ nome: "Veículo 1", placa: "ABC123", entrada: new Date().toISOString() });
    estacionamento.remover("ABC123");


```
- Função `ler`: Lê os veículos armazenados no localStorage e retorna um array de veículos.

```
    const veiculos = ler();
    console.log(veiculos); // Output: [{ nome: "Veículo 1", placa: "ABC123", entrada: "2023-07-11T12:34:56.789Z" }, ...]

```
- Função `salvar`: Salva os veículos no localStorage.

``` 
    const veiculos = [{ nome: "Veículo 1", placa: "ABC123", entrada: "2023-07-11T12:34:56.789Z" }, ...];
    salvar(veiculos);

```
- Função `adicionar`: Adiciona um novo veículo ao estacionamento, criando uma nova linha na tabela e salvando o veículo.

```
    adicionar({ nome: "Veículo 1", placa: "ABC123", entrada: new Date().toISOString() }, true);

```
- Função `remover`: Remove um veículo do estacionamento com base na placa, exibindo um alerta de confirmação e atualizando a tabela.
```
    remover("ABC123");

```
- Função `render`: Renderiza a tabela de veículos, removendo todas as linhas existentes e adicionando as linhas dos veículos armazenados.
```
    render();

```
- Evento `click` do botão `#cadastrar`: Captura o evento de clique no botão "Cadastrar", obtém os valores dos campos de entrada de texto e chama a função `adicionar` para cadastrar o veículo.

```
$("#cadastrar")?.addEventListener("click", () => {
    const nome = $("#nome")?.value;
    const placa = $("#placa")?.value;
    if (!nome || !placa) {
        alert("Os campos nome e placa são obrigatórios!");
        return;
    }
    adicionar({ nome, placa, entrada: new Date().toISOString() }, true);
});

```

### Considerações Finais

O projeto "Estacionamento" é uma aplicação simples e funcional para cadastrar e gerenciar veículos em um estacionamento virtual. Ele utiliza tecnologias web comuns, como HTML, CSS e JavaScript e TypeScript, para criar a interface e a lógica interativa.

Para executar o projeto, basta abrir o arquivo `index.html` em um navegador web compatível. Certifique-se de que todos os arquivos (HTML, CSS e JavaScript) estejam na mesma pasta ou mantenha a estrutura de diretórios conforme fornecida.

Qualquer dúvida ou sugestão, não hesite em me contatar! :smile:
