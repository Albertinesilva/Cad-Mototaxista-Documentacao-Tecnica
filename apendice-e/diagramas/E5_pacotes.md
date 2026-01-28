<h2 align="center">CAD-MOTOTAXISTA - Documentação Técnica</h2>

<br>

<h3>MODELAGEM ESTRUTURAL: DIAGRMA DE PACOTES</h3>

O diagrama de pacotes é uma ferramenta de modelagem estrutural que permite organizar e agrupar os elementos do sistema em unidades lógicas, evidenciando as dependências e relações entre seus componentes *(IBM, 2021)*. Esse tipo de diagrama é fundamental para reduzir a complexidade do software, promover a modularidade e facilitar a manutenção, além de fornecer uma visão clara da arquitetura e das interações entre diferentes partes do sistema.

<img src="../../assets/img/diagramas/Package-Cad-Mototaxista.svg" alt="Diagrama de Pacotes" style="display: block; margin: 0 auto; max-width: 100%; height: auto;">

No **CAD-MOTOTAXISTA**, o diagrama de pacotes foi construído com base na arquitetura MVC (Model-View-Controller), estruturando o sistema em três pacotes principais: <strong>View</strong>, <strong>Controller</strong> e <strong>Model</strong>. O pacote <em>View</em> é responsável pela apresentação de formulários, listas, relatórios e informações ao usuário. O pacote <em>Controller</em> gerencia os eventos e coordena a execução das operações, atuando como intermediário entre a camada de apresentação e a camada de dados. O pacote <em>Model</em> concentra as classes que representam as entidades do sistema, os serviços e as regras de negócio, assegurando a integridade e a consistência das informações manipuladas.

Essa organização evidencia a separação de responsabilidades e a lógica modular do sistema, permitindo compreender de forma clara como os componentes se relacionam e sustentam as funcionalidades do **CAD-MOTOTAXISTA**. Além disso, o diagrama facilita a manutenção e a evolução do software, ao tornar explícitas as dependências entre os pacotes e favorecer a reutilização de componentes, conforme apontado por *Lucidchart (2025)*.

<br>
