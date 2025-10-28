# Variant Family – Horizon-teemapohjan lisäosa

Tämä snippet lisää tuotesivulle (PDP) “Valitse malli” -osion, jossa näytetään samaan tuoteperheeseen kuuluvat tuotteet vaakarivissä.  
Nykyinen tuote korostuu, ja muut versiot linkittyvät klikkauksen kautta omille sivuilleen.  
Ratkaisu käyttää Shopify-metakenttää (`custom.variant_family`) tuotelistan hallintaan.

---

## ⚙️ 1. Metakentän luonti ja käyttö

1. Avaa **Asetukset → Metakentät ja metaobjektit**.  
2. Valitse **Tuotteet (Products)**.  
3. Luo uusi metakenttä nimeltä **Variant Family**.  
   - **Tyyppi:** Product list (Tuotelistaus)  
   - **Namespace ja key:** `custom.variant_family`  
4. Tallenna.  
5. Avaa **Tuotteet → Tuote jota haluat käyttää**
6. Scrollaa alas kunnes löydät kohdan **Tuotteen metakentät**
7. Valitse juuri luomamme metakenttä **Variant Family**
8. Voit tämän jälkeen valita tuotteet jotka linkittyvät kyseiseen tuotteeseen
9. Tässä tapauksessa valitse kaikki mahdolliset
10. Tallenna
11. Toista vaiheet 5-10 jokaiselle tuotteelle jonka haluat linkittää toisiinsa
12. Muista tallentaa!

---

## 🧩 2. Snippetin lisääminen PDP:lle

1. Tallenna snippet nimellä  
**snippets/variant-family.liquid**
2. Avaa **Verkkokauppa -> Teemat**
3. Etsi muokattu teema joka sisältää snippetin jota haluat käyttää
4. Valitse **Kustomoi**
5. Klikkaa Tuotetta, jotta pääset **tuotesivulle**
6. Tuotesivulla klikkaa vasemmalla olevaa kohtaa **Tuotteen tiedot**
7. Alle avautuu vaihtoehtoja etsi **Tuotteen kuvaus**
8. Vie hiiren kursori listan alle ja paina **+** symbolia
9. Etsi ja luo **Kustomoitu liquid (Custom liquid)**
10. Avaa juuri luotu **Kustomoitu liquid (Custom liquid)** ja lisää kenttään koodi 
`{% render 'variant-family' %}`
11. Tallenna muutokset ja esikatsele tuotesivua!

## 🧱 3. Fallback (kun data puuttuu)
Jos variant_family-metakenttä on tyhjä tai puuttuu, snippet ei tulosta mitään näin vältetään tyhjät alueet sivulla.

Jos jokin tuote listassa ei sisällä kuvaa, se näyttää harmaan laatikon (span.variant-swatch) kuvan sijasta.
Tämä toimii visuaalisena fallbackina ja säilyttää siistin ulkoasun.
