
#Pesquisar Endereço pelo CEP: Leia-me para Git

Este aplicativo web permite que os usuários pesquisem seus dados de endereço (bairro, complemento, rua, cidade e estado) inserindo seu CEP (código postal brasileiro). Ele utiliza a API ViaCEP (https://viacep.com.br/) para recuperar as informações.

##Funcionalidades

* Interface amigável com um campo de entrada claro para a entrada do CEP.
* Exibição intuitiva dos detalhes do endereço obtido.
* Validação de entrada para garantir um formato CEP válido (8 dígitos).
* Tratamento de erros para CEPs inválidos.


Como Funciona

O usuário insere seu CEP no campo de entrada com o cep.
Quando o usuário perde o foco no campo de entrada (toca fora ou pressiona Tab), a função getCEP() é acionada.
Dentro da função getCEP():
O CEP inserido é validado para garantir que contenha apenas caracteres alfanuméricos (letras e números) e tenha 8 dígitos.
Se inválido, uma mensagem de erro é exibida no campo de entrada do CEP.
Caso contrário, um objeto XMLHttpRequest (endereco) é criado para buscar dados da API ViaCEP usando uma solicitação GET.
O URL do endpoint da API é construído dinamicamente com base no CEP validado.
Após uma resposta bem-sucedida (código de status 200):
A resposta é analisada do formato JSON para um objeto JavaScript (jsonEndereco).
Os detalhes do endereço (bairro, complemento, rua, cidade e estado) são extraídos do objeto JSON.
Os campos de entrada correspondentes (logradouro, complemento, bairro, localidade, uf) são atualizados com os valores recuperados.
