```javaScript
        /**
        * Preenche automaticamente os campos de endereço ao digitar um CEP válido.
        * A busca é feita assim que o campo atingir 8 dígitos (sem precisar sair do campo).
        * Também limpa os campos se o CEP for inválido, incompleto ou apagado.
        */
        function buscarEnderecoPorCep() {
            const cepInput = document.getElementById('cep');
            const logradouroInput = document.getElementById('logradouro');
            const bairroInput = document.getElementById('bairro');
            const cidadeInput = document.getElementById('cidade');

            if (!cepInput || !logradouroInput || !bairroInput || !cidadeInput) return;

            const limparCamposEndereco = () => {
                logradouroInput.value = '';
                bairroInput.value = '';
                cidadeInput.value = '';
            };

            cepInput.addEventListener('input', async function () {
                const cep = this.value.replace(/\D/g, '');

                if (cep.length === 8) {
                    try {
                        const response = await fetch(`https://viacep.com.br/ws/${cep}/json/`);
                        const data = await response.json();

                        if (!data.erro) {
                            logradouroInput.value = data.logradouro || '';
                            bairroInput.value = data.bairro || '';
                            cidadeInput.value = data.localidade || '';
                        } else {
                            alert("CEP não encontrado. Verifique o número digitado.");
                        }
                    } catch (error) {
                        limparCamposEndereco();
                        console.error('Erro ao buscar o CEP:', error);
                        alert("Erro ao consultar o CEP. Tente novamente mais tarde.");
                    }
                } else {
                    limparCamposEndereco();
                }
            });
        }
```
