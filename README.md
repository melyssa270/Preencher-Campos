# Preencher-Campos
Minhas funções para preencher campos de um formulário a partir de um dataset.

function populaCampos(data){
	var campinhos = data.values;
	
	$.each(campinhos[0], function(key, value) {
        $("#" + key).val(value);
    });
	
	preencheCheckbox(campinhos);
}

function preencheCheckbox(data) {
    data.forEach(function(item) {
        for (var key in item) {
            if (item.hasOwnProperty(key)) {
                var valor = item[key];

                if (valor.length > 0) {      
                    var checkbox = $("[name='" + key + "']");
                    checkbox.prop('checked', true);
                    
                } else {
                    var checkbox = $("[name='" + key + "']");
                    checkbox.prop('checked', false);
                }
            }
        }
    });
}
