# Flex vs Grid
På sidan ligger avgångarna i `.tabla` med `display: grid` och `grid-template-columns: 1fr 1fr 1fr`. Både rader och kolumner behöver då vi vill placera avgångar i ett visst antal kolumner, i det här fallet tre. Med Flexbox är detta inte möjligt då allt lägger sig på en rad istället och kläms ihop.

Destinationskorten ligger i `.kort-rad` med `display: flex`. Det räcker med en riktning då vi vill att korten ska ordna sig på en rad och radbryta när de inte får plats. De är liknande kort i en riktning, inte ett rutnät.

# Ägarskap
Jag kan förklara varje rad jag pushat. AI får hjälpa mig tänka, men jag äger
koden och kan felsöka den utan att kopiera facit rakt av.

1. Varför sitter display: grid på .tabla och inte på varje .avgang?

För att .tabla är Grid-container:n medans .avgang:arna är Grid-items; de element som placerar sig inom Grid layout:en.

2. Vad gör 1fr jämfört med att sätta width: 33% på varje cell?

Det fördelar alla kolumner jämnt, varje cell blir automatisk lika bred som alla andra.
Att sätta width på varje cell innebär att vi måste ändra den manuellt om vi i framtiden vill ha mer eller mindre kolumner.

3. Vad händer om href="#tabla" pekar rätt men section saknar id="tabla"?

Ingenting, eftersom det inte finns någon ställe att hoppa/scroll:a till.

4. Varför behöver tabla en media query men destinationer ofta klarar sig med flex-wrap?

För att en Grid layout inte automatiskt bryter rad när alla element inte får plats. Så vi använder en media query för att istället själva bestämma när vi vill ha en annan kolumn-uppsättning.
