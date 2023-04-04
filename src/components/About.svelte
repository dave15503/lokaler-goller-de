<script>
    import ColumnContainer from "./ColumnContainer.svelte";



</script>

<div id="about">
    
<ColumnContainer row="4">
    <section>
        <h3>Impressum</h3>
        <p>
            Diese Website ist ein offensichtlicher Scherz. Der Lokale
            Goller ist der Öffentlichkeit nicht zugänglich und
            erwirtschaftet keinen Umsatz der ihn als Gewerbe
            meldepflichtig macht. Es handelt sich hierbei um eine
            geschlossene Gesellschaft.
            Alle erwähnten Inhalte sind fiktiv und jeglicher Bezug
            zu realen Orten und Personen ist reiner Zufall.
        </p>
        <p>
            Grüße gehen raus an den Steuerfahnder der das gerade liest.
        </p>
        <p>
            Kontakt für Feedback, Beschwerden und alle andere Anliegen: <a
            href="mailto: webmaster@lokaler-goller.de">webmaster@lokaler-goller.de</a>
        </p>
    </section>

    <section>
        <h3>Cookie- und Datenschutzrichtline</h3>
        <p>
            Diese Website ist rein statisch und erhebt weder
            persönliche Daten, noch nutzt sie aktiv irgendeine Art von
            Cookies. Deswegen ist sie nach Europäischem Recht auch nicht
            verpflichtet eine Einwilligung des Nutzers zu erfragen.
        </p>
    </section>

    <section>
        <h3>Lizenz und Urheberrecht:</h3>
        <p>
            Diese Website wird bereitgestellt als Open Source Software,
            der Quellcode ist für jedermann einsehbar im zugehörigen <a href="https://github.com/dave15503/lokaler-goller-de">Github-Repository</a>
        </p>
        <p>
            Dennoch macht sie Gebrauch von 3rd Party Bibliotheken und bildet die folgenden
            Inhalte von anderen Urheberrechtsinhabern ab:
        </p>
        <p>
            GITHUB®, the GITHUB® logo design, the INVERTOCAT logo
            design, OCTOCAT®, and the OCTOCAT® logo design are
            trademarks of GitHub, Inc., registered in the United States
            and other countries.
        </p>
        <p>
            Instagram and the Instagram logo design are trademarks of Instagram. LLC
        </p>
        <p>
            GoogleMaps and the GoogleMaps logo design are trademarks of Google
        </p>
    </section>

    <section>
        <h3>Vollständigkeit</h3>
        <p>
            Diese Website ist in der Entwicklung, wird also noch einige
            Lücken aufweisen und nicht auf jeder Plattform reibungsfrei
            funktionieren. Das Team des Lokalen Gollers bittet um
            Vertändnis. Diese Website besitzt ein öffentliches
            Repository auf Github, wo Bugs gemeldet oder eigens behoben
            werden können, wir danken für jeden Beitrag.
        </p>
    </section>
</ColumnContainer>

</div>
<style>
    #about {
        background-color: var(--secondary-background-color);
        grid-row: 1000/1000;
        grid-column: 1/5;
        padding: 20px;
        margin-top: 10px;
    }

    p {
        font-size: var(--minor-font-size);
    }

</style>