# mobilne

Kreirati dva fragmenta: ZadaciFragment i KorisniciFragment.
kako se kreiraju i gde:
🛠️ KAKO se kreiraju fragmenti (korak po korak)
✅ 1. Desni klik na paket
Right click na paket (npr. com.example.kolokvijum1)
Klikni: New → Fragment → Fragment (Blank)
✅ 2. Kreiranje prvog fragmenta
Name: ZadaciFragment
Layout name: fragment_zadaci
Klikni Finish

👉 Android Studio automatski napravi:

ZadaciFragment.java (ili .kt)
fragment_zadaci.xml
i dobijamo:

U Java folderu:
ZadaciFragment.java-logika
KorisniciFragment.java

U res/layout:
fragment_zadaci.xml-izgled
fragment_korisnici.xml

Dodati meni komponentu sa dve stavke Zadaci i Korisnici. (za ovaj primer)
Ovo je sledeći ključni korak — meni u Android aplikaciji. Radi se u res folderu, ne u Java kodu (osim povezivanja).

📍 GDE se pravi meni?

U projektu idi na:
app → res → menu
📌 Ako nema foldera menu:
Desni klik na res
New → Android Resource Directory
Resource type: menu
🛠️ KAKO se pravi meni
✅ 1. Desni klik na menu
New → Menu resource file
✅ 2. Naziv fajla
npr: menu_main.xml
🧾 ŠTA ide u menu_main.xml
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:id="@+id/zadaci"
        android:title="Zadaci"/>

    <item
        android:id="@+id/korisnici"
        android:title="Korisnici"/>
</menu>

🔗 KAKO se povezuje sa MainActivity

U MainActivity.java dodaješ:<java>
1. Učitavanje menija
@Override
public boolean onCreateOptionsMenu(Menu menu) {
    getMenuInflater().inflate(R.menu.menu_main, menu);
    return true;
}

2. Reakcija na klik
@Override
public boolean onOptionsItemSelected(MenuItem item) {

    if(item.getItemId() == R.id.zadaci){
        // prikaži ZadaciFragment
    } else if(item.getItemId() == R.id.korisnici){
        // prikaži KorisniciFragment
    }

    return true;
}
