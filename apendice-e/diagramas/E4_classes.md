<h2 align="center">CAD-MOTOTAXISTA - Documentação Técnica</h2>

<br>

<h3>MODELAGEM ESTRUTURAL: DIAGRAMA DE CLASSES E ENUMERAÇÕES</h3>

A modelagem estrutural tem como objetivo representar a organização estática do sistema, descrevendo suas classes, atributos, métodos e os relacionamentos estabelecidos entre elas. Segundo a *IBM (2021)*, essa abordagem é essencial para compreender a arquitetura interna do software, servindo de base para as fases de implementação, testes e manutenção. No contexto da engenharia de software, os diagramas estruturais, especialmente o diagrama de classes, permitem a visualização clara das responsabilidades de cada componente e das dependências existentes, contribuindo para a padronização e robustez da modelagem.

### Diagrama de Classes

Os diagramas de classes representam a estrutura estática de um sistema, evidenciando suas entidades, atributos, métodos e os relacionamentos existentes entre elas. Essa representação visual permite compreender de forma organizada a arquitetura do software, proporcionando uma visão abstrata das interações e responsabilidades de cada classe. Além disso, contribui significativamente para a análise, desenvolvimento e manutenção do sistema, auxiliando na identificação de dependências e na padronização da modelagem das funcionalidades (Draw.io, 2025).

Para assegurar clareza e melhor compreensão da estrutura do sistema, o diagrama de classes do **CAD-MOTOTAXISTA** foi organizado em duas partes complementares. Essa divisão possibilita evidenciar, de maneira detalhada, as principais entidades do sistema, suas características e relações, oferecendo uma visão abrangente e de fácil interpretação da arquitetura do software.

#### Diagrama de Classes – Parte 1

A primeira parte do diagrama concentra-se nas classes fundamentais relacionadas à autenticação, autorização e gerenciamento de usuários. Destaca-se a classe abstrata `AbstractEntity`, que fornece o atributo identificador (`id`) e métodos comuns, promovendo padronização e redução de redundância entre as entidades do sistema.

<img src="../../assets/img/diagramas/Class-Cad-Mototaxista-Parte-1.svg" alt="Diagrama de Classes Parte 1" style="display: block; margin: 0 auto; max-width: 100%; height: auto;">

As classes `Usuario`, `Funcionario` e `Cliente` estruturam os diferentes perfis de acesso, estabelecendo distinções claras entre usuários administrativos e usuários finais. A classe `Perfil` gerencia os níveis de permissão, assegurando que cada usuário possua acessos compatíveis com suas responsabilidades no sistema.

Complementarmente, a classe `Token` reforça os mecanismos de segurança ao registrar informações sobre tokens temporários utilizados em processos como ativação de contas e redefinição de senhas, prevenindo reutilizações indevidas. A classe `Mail` viabiliza a comunicação automatizada por e-mail, armazenando dados como remetente, destinatário, assunto e conteúdo, essenciais para notificações e validações de segurança.

Além disso, as classes `Endereco` e `Contato` são associadas a usuários e clientes, garantindo a integridade e a organização dos dados pessoais. As classes de registro, como `RegistroClienteContato` e `RegistroAuditoria`, asseguram a rastreabilidade das ações realizadas no sistema, permitindo auditoria e monitoramento das interações e alterações efetuadas, aspecto fundamental em sistemas voltados à gestão pública e à fiscalização.

#### Diagrama de Classes – Parte 2

Complementando a estrutura apresentada na Parte 1, o Diagrama de Classes – Parte 2 concentra-se no domínio dos condutores e de suas respectivas motocicletas. A classe central `Condutor` armazena dados pessoais — como nome, CPF, RG e tipo sanguíneo — e dados operacionais, incluindo situação do cadastro, datas de criação e modificação, bem como responsáveis pelas alterações, assegurando controle e rastreabilidade.

<img src="../../assets/img/diagramas/Class-Cad-Mototaxista-Parte-2.svg" alt="Diagrama de Classes Parte 2" style="display: block; margin: 0 auto; max-width: 100%; height: auto;">

A classe `Condutor` se associa diretamente às classes `Endereco` e `Contato`, garantindo que cada condutor possua obrigatoriamente um endereço registrado e informações de contato válidas. O relacionamento com a classe `Cnh` permite gerenciar dados da carteira de habilitação, como número, validade e categoria, assegurando conformidade legal e controle dos registros profissionais.

Outro aspecto relevante é a modelagem das motocicletas. Cada condutor deve estar obrigatoriamente associado a uma única `Motocicleta`, e cada motocicleta pertence exatamente a um condutor, caracterizando um relacionamento do tipo 1..1. A classe `Motocicleta` contém atributos como placa, ano de fabricação, observações, tipo de placa e situação do veículo (própria ou locada). Sua associação com as classes `MotoModelo` e `MotoMarca` garante a padronização e a correta identificação dos veículos, estabelecendo uma hierarquia clara entre marcas e modelos.

No contexto geral, essa modelagem estrutural é fundamental para organizar de forma consistente as informações do sistema, assegurando a integridade dos cadastros e facilitando a manutenção, evolução e escalabilidade do software.

### Diagrama de Enumerações

O Diagrama de Enumerações ilustra os tipos enumerados da camada de domínio do sistema CAD-MOTOTAXISTA. As enumerações definem conjuntos fixos e limitados de valores, garantindo integridade dos dados, padronização das informações e redução de inconsistências durante o processamento das regras de negócio.

<img src="../../assets/img/diagramas/Enumeracoes.svg" alt="Diagrama de Enumerações" style="display: block; margin: 0 auto; max-width: 100%; height: auto;">

No domínio dos condutores e veículos, destacam-se as enumerações `ETipoSanguineo`, que define os tipos sanguíneos possíveis; `EModalidadeDeCondutor`, que distingue se o profissional atua como mototaxista, motofretista ou ambas as modalidades; e `ECategoria`, que lista as categorias da CNH. Para o contexto das motocicletas, `ETipoPlaca` padroniza os tipos de placa (Mercosul ou antiga), enquanto `ESituacaoMoto` define se a motocicleta é própria ou locada.

No âmbito da segurança e do controle de acesso, a enumeração `ETipoPerfil` estabelece os níveis de permissão (Administrador, Funcionário ou Cliente), sendo essencial para o funcionamento da classe `Usuario`. A enumeração `SecureTokenType` especifica o propósito de cada token, como ativação de conta, redefinição de senha ou verificação de código. Por fim, `ResultadoAtivacao` padroniza as respostas do sistema durante os processos de ativação, indicando estados como “ativado”, “já ativado” ou “token inválido”.

O uso sistemático de enumerações constitui uma prática consolidada da engenharia de software, pois promove consistência, robustez, confiabilidade e clareza na implementação das regras de negócio, contribuindo para a qualidade e a manutenção do sistema como um todo.


<br>
