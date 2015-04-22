# Login-ajax-
# Gilberto
Código de Ajax para lógin. ¡Problema al comparar parámetro de resultado de usuario!

<script type="text/javascript">
	$(document).on('ready', function(e){
		$('#login').on('click', function(e){
			
			var pass = $('#pasw').val();
			var usuario = $('#user').val(); 
			
			$.ajax({
          type: "POST",
          url: "validarCuentas.php",
          data: {user: usuario, pass: pass},
          cache: false,
          beforeSend: function(){$("#login").val('Connecting...');},
          success: function(data){//El detalle es que el parametro si recoje el valor 'administrador'
            if(data =="administrador"){// No entra y data es administrador  
            	$("body").load("Administrador.php").hide().fadeIn(1500).delay(6000);
            }
          }
      });
			
			return false;

		});
	});
</script>
