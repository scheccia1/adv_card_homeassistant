# Advanced Card Room homeassistant

![Screenshot 2024-11-14 220515](https://github.com/user-attachments/assets/37a3b0cf-c7b1-4bc7-90ef-6b9c841d2bb5)

Installare da HACS:
1) button-card
2) mushroom

sono presenti i seguenti file contenti il codice per card:
1) button.txt - pulsante semplice (usa solo button-card)
2) button_temp.txt - pulsante semplice con indicatore temperatura
3) adv_card_2_pulsanti.txt - card per stanza con 2 pulsanti
4) adv_card_3_pulsanti.txt - card per stanza con 3 pulsanti

E' presente un file packages, non è indispensabile io l'ho fatto perchè ogni volta che cambio/modifico un dispositivo devo trovare il sensore per ogni scheda e cambiarlo, cosi facendo inserisco tutto in un package e lo sostituisco solamente li. <br><br>

Il modo più semplice per utilizzare le schede è inserire i propri sensori.<br><br>
per utilizzare la ventola animata, inserire in seguente codice nello style del pulsante il seguente codice:
<code>
style: |
	ha-card {
		background: none;
		border: none;
		}
	 {% if states('MIO_SENSORE') == 'on' %}
		ha-state-icon {
		  animation: wobbling 0.7s linear infinite;
			}
		@keyframes wobbling {
		  0% {transform: rotate(360deg);}
		  100% {transform: rotate(0deg);}
		}
	{% endif %}
 </code>

i codici colori usati nelle schede sono: <br>
blu -> #343b48 - #768ec0 <br>
verde -> #343f36 - #759f7b <br>
giallo -> #48422f - #c2ab60 <br>
rosso -> #453432 - #b4756d <br>
