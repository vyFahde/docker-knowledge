# Principais Pontos
[[O que é uma imagem]]

### **Sistema Operacional e Kernel**
  - O kernel atua como intermediário entre os programas em execução e o hardware físico.
  - Facilita a comunicação através de chamadas de sistema, permitindo que os programas solicitem recursos como armazenamento de arquivos ou memória.

### **Problemas de Alocação de Recursos**
  - Exemplo com programas que requerem versões diferentes do Python.
  - Situação ilustra o problema de recursos conflitantes.

### **Namespacing**
  - Permite ao sistema operacional segmentar recursos de hardware.
  - Cada programa acessa apenas os recursos que necessita, evitando conflitos (ex.: Chrome pode acessar Python 2 enquanto Node.js acessa Python 3).

### **Recursos de Software**
  - Namespacing aplica restrições a acessos a arquivos, dispositivos de rede e comunicação interprocessos.
### **Grupos de Controle (Control Groups)**
  - Reforçam o namespacing limitando a quantidade de recursos (CPU, memória, largura de banda) que um processo pode utilizar.
  - Juntos, namespacing e grupos de controle criam um container.

### **Conceito de Container**
  - Um container não deve ser visto como uma entidade física, mas como um agrupamento lógico de processos e seus recursos associados.

 ### **Relação entre Imagens e Containers**
  - Imagem é um snapshot do sistema de arquivos que contém os arquivos e diretórios necessários para criar um container.
  - Ao executar uma imagem, o kernel isola uma seção de recursos e a preenche com o conteúdo da imagem, criando efetivamente um container em execução.

## Conclusão
A aula desmistifica o conceito de containers, explicando os mecanismos subjacentes, incluindo as funções do kernel, namespacing, grupos de controle e a relação entre imagens e containers. O palestrante encoraja a exploração adicional de containers e imagens nas seções seguintes.