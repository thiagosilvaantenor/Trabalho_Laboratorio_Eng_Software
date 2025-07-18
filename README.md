# Carômetro
`Plataforma para conectar egressos (ex-alunos) da FATEC ZL, feita com: Java,Spring,Thymeleaf e MySQL`

## Integrantes do grupo:
* Sabrina Carvalho Da Silva
* Sara Félix Souza
* Thiago Silva Antenor
* Vitoria Rodrigues Borges

## Tecnologias
- Java 17
- Spring
- Maven
- Thymeleaf
- MySQL
- Lombok

## Atores
- `Administrador`: Vai cadastrar os cursos da FATEC, validar os egressos para que possam aparecer na página de postagem e cadastrar alunos, via envio de arquivo `.csv`, para que possam ser contatados quando virarem egressos para ingressar na plataforma.
- `Coordenador`: Pode filtrar a lista de egressos para ver somente os do seu curso
- `Egresso`: Vai se cadastrar, necessitando aceitar o termo de divulgação das informações presentes na postagem, e após validado pelo administrador vai aparecer na página de postagens
- `Aluno`: Pode se cadastrar, informando os dados de contato para quando se tornar um egresso.

## Para rodar:
- Tenha instalado: Java 17 ou maior, Maven e Lombok
- Escolha sua IDE Java de preferência, a exemplo o Eclipse, importe o projeto e instale as dependencias, caso precisar usar o terminal use o comando: `mvn install`
- Edite o `application.properties` ele se encontra em: `main/src/main/resources/application.properties` talvez você precise trocar:
  - Linha 4 número da porta em que está rodando o MySQL, exemplo caso esteja rodando em 3307: spring.datasource.url=jdbc:mysql://`localhost:3307`/carometro?createDatabaseIfNotExist=true
  - Linhas 5 e 6 seu username e sua senha do MySQL, exemplo seu username é root e sua senha é teste123: spring.datasource.username=`root`, spring.datasource.password=`teste123`
  - Linha 7, porta em que vai rodar o servidor, caso queira rodar em 8081: server.port=`8081`
- Pronto, basta rodar o `/main/src/main/java/br/com/carometro/CarometroSpringApplication.java`, ou usar o comando `mvn spring-boot:run`
- **Para testar, cadastre um administrador, faça o login e cadastre os cursos para que os outros atores possam interagir com o sistema**

## Explicação de utilização prevista
- Adminstrador realiza o cadastro, realiza o login, cadastra os cursos da FATEC
- Caso nécessário o adminsitrador pode editar seu cadastro
- Coordenador e Egresso podem se cadastrar
- Ambos podem se logar e editar o cadastro
- Administrador valida o cadastro do egresso:
  - Se realmente é um egresso
  - Se a foto é valida para aparecer na postagem e perfil
  - Se os comentários sobre a FATEC e o Geral são válidos para aparecer na postagem e perfil
- Egresso agora é visivel na página de postagens
- Qualquer usuário, mesmo sem estar logado, pode ver as postagens
- Caso o egresso edite sua foto ou comentários, eles devem ser validados novamente para serem exibidos na postagem.


## Preview

* Inicio:
  * `localhost:8080/`
  * ![Inicio](https://github.com/user-attachments/assets/b48ab123-0ab7-4871-b3aa-8ac1e471deff)
    
* Saiba Mais:
  * `localhost:8080/saibaMais`
  * ![Início Carômetro — Mozilla Firefox 2025-07-02 10-34-25](https://github.com/user-attachments/assets/b80e63c0-47a6-4871-b281-2660372029b5)
    
* Login:
  * `localhost:8080/login`
  * ![Login](https://github.com/user-attachments/assets/e43faf40-9659-4e5c-a0bf-5cf85335aef2)
    
* Egresso:
  * Cadastrar: `localhost:8080/egresso/formulario`
  ![Cadastro de Egresso — Mozilla Firefox 2025-07-02 11-19-26](https://github.com/user-attachments/assets/dd1e5086-c360-438c-8621-98cdbf857394)
  * Postagens de egressos validados: `localhost:8080/egresso`
  ![Postagens de Egressos](https://github.com/user-attachments/assets/3445d540-e7f3-445d-85ea-96f65828efbf)
  * Perfil de egresso: `localhost:8080/egresso/perfil/{id}`
  ![Perfil do Egresso — Mozilla Firefox 2025-07-02 10-47-28](https://github.com/user-attachments/assets/4f8ff819-cb44-4e6d-8b88-174ec8958926)
  * Home (precisa estar logado): `localhost:8080/egresso/index`
  ![home do egresso](https://github.com/user-attachments/assets/d86da2a5-9c27-45c7-be74-b26af807e85f)

* Administrador:
  * Cadastrar: `localhost:8080/admin/formulario`
  ![cadastro admin](https://github.com/user-attachments/assets/591f1af8-ab38-4daf-b881-6b6230f9ac9a)
  * Exibir, Editar e excluir (Acessivel apenas ao Admin): `localhost:8080/admin`
  ![listagem de admin](https://github.com/user-attachments/assets/a6873336-c139-41c3-936a-a2193b5fb22b)
  * Home (deve estar logado): `localhost:8080/admin/index`
  ![Home do admin](https://github.com/user-attachments/assets/b54d0cb0-33f4-490b-a2f5-b996f9f58b5f)
  * Cadastrar Cursos (deve estar logado): `localhost:8080/curso/formulario`
  ![cadastrar cursos](https://github.com/user-attachments/assets/4d623855-72cb-4fe1-9c77-8f38812ca998)
  * Exibir, Editar e excluir cursos: `localhost:8080/curso`
  ![listagem de cursos](https://github.com/user-attachments/assets/fc3f540a-fe95-40b3-847a-c155282bfd70)
  * Validar Egressos (deve estar logado): `http://localhost:8080/admin/validarPostagem`
  ![validar egressos](https://github.com/user-attachments/assets/cec38ec5-af3d-41f8-a244-9dc1df207610)
  * Cadastrar Alunos por envio de arquivo (deve estar logado): `http://localhost:8080/aluno/cadastroPorArquivo`
  ![cadastrar aluno por arquivo](https://github.com/user-attachments/assets/9b5e64d1-c55d-4b5d-bfea-d956a1737f74)

* Coordenador
  * Cadastrar: `localhost:8080/coordenador/formulario`
  ![cadastrar coordenador](https://github.com/user-attachments/assets/b1edead1-8577-4b7a-8fff-3f0ce9ba0165)
  * Exibir, Editar e excluir (Acessivel apenas ao Admin): `localhost:8080/coordenador`
  ![listagem de coordenador](https://github.com/user-attachments/assets/e01a5181-0d8d-4045-b257-f41451cec3f7)
  * Home (deve estar logado): `localhost:8080/coordenador/index`
    ![Home do coordenador](https://github.com/user-attachments/assets/8e80782b-1240-4a3f-9f7e-2145dec493e4)
  * Ver postagens do curso do coordenador logado (redireciona para postagens dos egressos, com o filtro de curso selecionado para o curso do coordenador): `http://localhost:8080/egresso/filtrar?&cursoId={id do curso do coordenador}`
  ![Ver postagens do curso](https://github.com/user-attachments/assets/15f758b7-4aaa-40c6-9012-2a2d9bfe1938)
 
* Aluno
  * Cadastro: `localhost:8080/aluno/formulario`
    ![cadastrar aluno](https://github.com/user-attachments/assets/cb41ba0c-92ad-4d1d-a391-87b23f6212bf)
  * Exibir, Editar e excluir (acessivel apenas ao admin): `http://localhost:8080/aluno`
    ![listar alunos](https://github.com/user-attachments/assets/f7a33d8e-e476-40a9-b6dd-84cfd0e42037)
  * Home (deve estar logado):
    ![home aluno](https://github.com/user-attachments/assets/945fadc3-b843-4cf5-b828-7c85e20a3032)

    
