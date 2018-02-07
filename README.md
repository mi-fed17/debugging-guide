# Felsökningsguide
> Steg att följa om din JavaScriptkod inte fungerar som den ska.

1. **Kolla så att du har stavat rätt på alla variabler**
2. Kolla igen så att du har stavat rätt på alla variabler (**SERIÖST**)
3. Försöker du att komma åt ett värde i **DOM**en? Dubbelkolla så att du har skrivit samma namn på det `id`, `class` eller `<tag>` du försöker komma åt både i HTML-koden samt i JavaScript-koden.
4. Försöker du lyssna på ett **event** men det fungerar inte? Öppna **Console** i *Chrome/Firefox Developer Tools*, ser du detta meddelande?
![https://i.imgur.com/1XI6rEl.png](https://i.imgur.com/1XI6rEl.png)
Det betyder att du försöker lägga på en _event listener_ på ett element som inte existerar. Har du hämtat försökt hämtat ett element som inte finns kommer variablen du sparar i JavaScript att bli `null` och ingenting kan köras på den. Meddelandet säger också på vilken rad som felet är, i detta fall är det på rad **4** i min egen fil `main.js`. Gå till den raden och se över vad som är `null`.
5. Har du hämtat element med `querySelectorAll`/`getElementsByClassName`/`getElementsByTagName`? Variablen är **alltid** en array, vilket betyder att du måste loopa igenom den alternativt plocka ut ett element på ett visst index.
```js
const links = document.getElementByTagName('a');

links.style.color = 'hotpink';    // This will not work, loop first!
links[0].style.color = 'hotpink'; // This will work, first index, one item
```
6. Vet du inte om du har fått rätt element eller om din klickfunktion fungerar? Testa använd `console.log` och skriv ut variablen eller ett meddelandet till `console` för att se så att någonting fungerar. [Läs mer om hur du kan använda `console` här](https://dev.to/worldclassdev/leveraging-the-power-of-the-javascript-console-in-development-24ap)
7. Vill du slippa `console.log` hela tiden för att se vad som händer i koden? Öppna **Sources** i *Chrome/Firefox Developer Tools*. Här kan du sätta ut **Breakpoints** genom att trycka på linjenumret bredvid koden så att siffran blir blå. Då säger du åt Chrome att stanna upp koden vid det tillfället så att du kan se vad som händer och koden kommer inte att fortsätta förän du säger åt den att den ska göra det. Till vänster ser du alla dina filer. I mitten är en editor och till höger är information om koden.
![https://i.imgur.com/JYPpvnp.png](https://i.imgur.com/JYPpvnp.png)
I det här exemplet kan vi se att `x` och `y` har blivit till _10_ t.ex. Till höger ser vi även vad resterande variabler har för värden (`first`, `second`). Detta är ett bra verktyg för att inspektera variabler och hur kod körs. När du är klar med att inspektera så trycker du på den blåa play-knappen, alternativt trycker F8. Vill du ta bort denna breakpoint så trycker du på den igen. Du kan sätta ut hur många breakpoints du vill.
![https://i.imgur.com/jBvSFk3.png](https://i.imgur.com/jBvSFk3.png)