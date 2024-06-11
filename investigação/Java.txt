document.getElementById('formulario').addEventListener('submit', function(e) {
    e.preventDefault();
    
    let contador = 0;

   
    for (let i = 1; i <= 10; i++) {
        const resposta = document.querySelector(`input[name="questao${i}"]:checked`).value;
        if (resposta === 'sim') {
            contador++;
        }
    }

    let classificacao;
    if (contador === 5) {
        classificacao = 'Suspeita';
    } else if (contador >= 6 && contador <= 8) {
        classificacao = 'Cúmplice';
    } else if (contador >= 9 && contador <= 10) {
        classificacao = 'Culpada';
    } else {
        classificacao = 'Inocente';
    }


    document.getElementById('resultado').innerHTML = `<p>Classificação: ${classificacao}</p>`;});