# Security2
Eindopdracht security 2

Wij hebben ipv een database de gegevens opgeslagen in localStorage omdat dit op hetzelfde neerkomt.
Onze gebruikte techniek is de library van crypto-js om de gegevens te encrypten en te decrypten.
Hier gebruiken we de AES manier : De Advanced Encryption Standard (AES) is de U.S. Federal Information Processing Standard (FIPS).
CryptoJS ondersteunt AES-128, AES-192, en en-256. Het zal een variant kiezen aan de hand van de groote van de tekst.
Wanneer er een passphrase wordt gebruikt zal deze een 256-bit key genereren.

# Encrypten gegevens

var encrypted = CryptoJS.AES.encrypt("Message", "Secret Passphrase");
Hier is message onze geheime bericht  en de Secret Passphrase is onze naam en onze wachtwoord.
Zodat we later onze geheim bericht weer kunnen decoderen met onze naam en wachtwoord.

var encrypted = CryptoJS.AES.encrypt(text, naam + " " +ww);



Nu slaan we de gegevens op in de localStorage localStorage.setItem("message", encrypted);


# Decrypten gegevens

Nu moeten we onze encrypted bericht weer ophalen d.m.v. 
var encrypted = localStorage.getItem("message");

Daarna halen we de naam en wachtwoord op die wordt ingevuld in het formulier

var naam = $("#name").val();
var ww = $("#ww").val();

En nu kunnen we d.m.v. deze gegevens ons bericht weer decoderen

var decrypted = CryptoJS.AES.decrypt(encrypted, naam + " " + ww);





