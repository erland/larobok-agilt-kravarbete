# Exportguide

All export ska utgå från `docs/export-metadata.yaml` och kapitelordningen i metadatafilens `chapters`.

## EPUB

- EPUB ska ha luftig layout.
- Ingen textbaserad innehållsförteckning ska infogas som separat kapitel.
- Metadata ska använda titel, undertitel, författare, språk, identifierare och datum från `export-metadata.yaml`.

## PDF

- PDF ska ha innehållsförteckning före inledningen.
- Innehållsförteckningen ska genereras från rubrikstrukturen.
- Markdown ska renderas till riktiga rubriker, listor, fetstil, kursiv och kod-/citatblock.

## DOCX

- Markdown ska renderas, inte kopieras som rå markdown.
- Rubriker, listor och tabeller ska bli riktiga DOCX-format.

## Bildkontroll

- Omslagsbild är planerad men ännu inte genererad.
- Inga inre illustrationer används i första versionen.
- Vid export med omslag ska `cover_image` fyllas i när omslaget finns.
