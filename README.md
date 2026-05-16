# lnpg-cap9-subprogramas-diogo-henrique
Diogo Henrique - BSI 2026.1
Tarefa 1 — Modularização em Java:
Quebrar o codigo em partes permite ter uma legibilidade e reutilização melhor, facilitando de testar e alterar. 

Tarefa 2 - Apesar do codigo ser pequeno, havia uma mistura de responsabilidade (Leitura, cálculo e impressão). O cálculo do subtotal, desconto e total ficavam espalhados no meio da lógica principal, misturados com input/output. Numeros magicos (0.10, 0.05, 200, 500) não tinham nomes claros. O cálculo do subtotal, desconto e total ficavam espalhados no meio da lógica principal, misturados com input/output. Se quisesse calcular o desconto em outro lugar (ex: relatório, carrinho web, etc.), teria que copiar e colar o if. Com a criação das funções, várias partes puderam ser reutilizadas. As funções de cálculo (calcular_subtotal, calcular_desconto, calcular_total) são puras (não têm efeitos colaterais), o que permite usá-las em testes automatizados, em uma API, em um sistema de e-commerce, etc. A função imprimir_cupom() pode ser facilmente adaptada para gerar PDF, HTML ou salvar em arquivo.

Tarefa 3 - Passagem por valor significa que uma cópia do valor da variável é enviada para o método, e não a variável original. Java utiliza passagem de parâmetros por valor (pass-by-value) para todos os tipos primitivos (int, double, boolean, etc.). Quando utilizamos alterarNumero(numero); O Java cria uma cópia do valor 50 e coloca nessa cópia dentro do parâmetro x. A variável numero que está no main continua existindo independentemente. Foi copiado o conteúdo (o valor) da variável, não a referência da variável em memória. Por isso, qualquer alteração feita em x dentro do método só afeta a cópia local, e não a variável original.
Tipos primitivos → sempre são passados por valor (cópia).
Objetos (classes) são passados por referência (o endereço do objeto é copiado), mas o mecanismo base ainda é "pass-by-value" (cópia da referência).

Tarefa 4 - Java não possui passagem por referência verdadeira (pass-by-reference). Java utiliza exclusivamente passagem por valor (pass-by-value) em todos os casos, como mostrado tambem na tarefa anterior. Quando chamamos aplicarDesconto(produto); O Java copia o valor da referência (o endereço de memória do objeto). Ou seja, é copiado o "caminho" para o objeto, não o objeto em si.
Por que as alterações no objeto permanecem após a chamada? - Porque tanto o parâmetro p (dentro do método) quanto a variável produto (no main) apontam para o mesmo objeto na memória heap.
Quando modificamos p.preco, estamos alterando o conteúdo do objeto compartilhado. A cópia que foi passada é da referência, não do objeto.
