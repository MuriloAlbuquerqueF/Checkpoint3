# Checkpoint3 -Trabalho de arrumar um código - UNINOVE

Violações do SRP (Single Responsibility Principle)
Métodos: AdicionarUsuario, RealizarEmprestimo, RealizarDevolucao, EnviarEmail, EnviarSMS
Problema: A classe GerenciadorBiblioteca faz muita coisa diferente, como manipulação de livros, usuários, empréstimos, cálculo de multas e envio de notificações.
Por que é ruim: Isso torna o código difícil de manter e testar, e também viola o princípio de coesão, por exemplo: qualquer alteração na lógica de notificação, por exemplo, exige mudanças nessa classe gigante.

Violações do OCP (Open/Closed Principle)
Método: RealizarEmprestimo
Problema: Se quisermos adicionar um novo tipo de notificação, precisamos modificar o método RealizarEmprestimo.
Por que é ruim: O código deveria estar aberto para extensão, mas fechado para modificação. Isso indica acoplamento excessivo entre lógica do negócio e implementação das notificações.

Violações do DIP (Dependency Inversion Principle)
Métodos: EnviarEmail, EnviarSMS
Problema: A classe depende diretamente de implementações concretas de envio de notificação.
Por que é ruim: Isso dificulta testes automatizados e a reutilização do código, pois não usamos interfaces para desacoplar as dependências.

Violações de Clean Code - Nomes Pouco Descritivos
Método: AdicionarLivro, AdicionarUsuario, RealizarDevolucao
Problema: Apesar de os nomes dos métodos serem bons, algumas variáveis como l, u não são claras, por isso, teria que se ler o método inteiro para entender o que são.
Por que é ruim: Nomes devem ser autoexplicativos. O leitor deve entender o que está acontecendo sem precisar ler todo o método.

Violações do ISP (Interface Segregation Principle)
Problema: Não há interfaces para separar responsabilidades distintas. Por exemplo, não tem interface para INotificacaoService ou IRepositorioLivro.
Por que é ruim: Tudo está acoplado em uma classe gigante. Um cliente que só quer consultar livros, por exemplo, fica dependendo de métodos de notificação e empréstimo.
