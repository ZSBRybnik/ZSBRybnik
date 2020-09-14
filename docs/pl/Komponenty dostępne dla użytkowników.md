# Komponenty dostępne dla użytkowników

Osoby obsługujące wpisy oraz podstrony przez bazę danych mają do dyspozycji poniższe komponenty

## Elementy Markdown'a

### Zwykły tekst

Zapis zwykłego tekstu:

```txt
Integer porta elit eu mauris vehicula dignissim quis ac est. Proin scelerisque congue eros. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Curabitur congue nisi ut mattis mollis. Phasellus blandit, purus ac eleifend viverra, justo ipsum fringilla justo, suscipit sodales dui tortor nec arcu.

Morbi risus ante, eleifend sed auctor et, fringilla ut enim. Phasellus risus magna, commodo sit amet semper vitae, iaculis in erat. Vestibulum mollis elit ac lorem volutpat imperdiet.
```

Zapis tak jak powyższy zostanie przemianowany na stronie w:

```tsx
<TextBlock value="Integer porta elit eu mauris vehicula dignissim quis ac est. Proin scelerisque congue eros. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Curabitur congue nisi ut mattis mollis. Phasellus blandit, purus ac eleifend viverra, justo ipsum fringilla justo, suscipit sodales dui tortor nec arcu." />
<TextBlock value="Morbi risus ante, eleifend sed auctor et, fringilla ut enim. Phasellus risus magna, commodo sit amet semper vitae, iaculis in erat. Vestibulum mollis elit ac lorem volutpat imperdiet." />
```

Pusta linia oznacza wygenerowanie nowego akapitu. Napisanie tego tekstu ciągiem bez pustych liń spowoduje utworzenie się tylko jednego komponentu `TextBlock` na stronie.

### Kod

Zapis kodu:

```md
3 razy tylda po czym podajemy skrót języka w 2 literach
// kod
3 razy tylda
```

Przykładowy kod w Rust'cie:

```rs
fn main() {
  let exampleValue: usize = 12;
  println!("{}", exampleValue);
}
```

Zapis tak jak powyższy zostanie przemianowany na stronie w:

```tsx
<CodeBlock value=`
fn main() {
  let exampleValue: usize = 12;
  println!("{}", exampleValue);
}
` language="rs" />
```

### Listy

Zapis listy:

```md
- wartość 1.
- wartość 2.
- wartość 3.
```

## Elementy JSX

## Embed

Zapis ramki:

```tsx
<Embed url="Adres linku" isTwitter />
```

Parametr `isTwitter` jest opcjonalny. Jeśli posiadamy więcej niż jednego tweet'a w poście lub na podstronie to należy umieścić go tylko w pierwszym tweet'cie

### Link

Zapis link'u:

```tsx
<Link href="Adres linku" title="Tytuł linku" toDownload inNewCard />
```

Parametr `toDownload` jest opcjonalny.  
Parametr `inNewCard` jest opcjonalny.

### Obrazek

Zapis obrazka:

```tsx
<Image src="Źródło" alt="Tekst alternatywny" text="Mały tekst pod obrazkiem" />
```

Parametr `text` jest opcjonalny.

### Tabela

Zapis tabeli:

```tsx
<Table>HTML...</Table>
```

Jako HTML muszą wpaść prawidłowe znaczniki tabeli. Tabela automatycznie dodaje `<tbody>` więc należy je pominąć.

### Galeria

Zapis galerii:

```tsx
<Gallery sources={["link", "link"]} types={["image", "image"]} />
```

Jako linki dla galerii mogą występować: zdjęcia, filmiki na YouTube, mapa google.  
Parametr `types` przyjmuje: `image`, `video` oraz `youtube`.

### Model 3D

Zapis modelu 3D:

```tsx
<ThreejsView modelPath="Źródło" zPosition="Pozycja względem osi Z" yPosition="Pozycja względem osi Y" xPosition="Pozycja względem osi X" />
```

Parametr `zPosition` jest opcjonalny.  
Parametr `yPosition` jest opcjonalny.  
Parametr `xPosition` jest opcjonalny.  

### TikTok

Zapis TikTok'a:

```tsx
<TikTok>blockquote od TikTok'a...</TikTok>
```

Jeśli chcemy umieścić TikTok'a należy:

1. Udać się na stronę z TikTok'iem.
2. Kliknąć w czerwony guzik z pustym tagamiem HTML'a `</>` podpisany jako `Pobierz kod osadzony`.
3. Skopiować wyświetlony kod od z pominięciem tagu `<script>` czyli sam `blockquote`.
