# TypeScript çalışma notları

Türkçe açıklamalarla **1.000 başvuru maddesi**, 10 bölüm.

## Çalışmaya başla

- [Başlıklara göre düzenlenmiş çalışma notları](notes/typescript.md)
- [1.000 maddelik JSON verisi](data/typescript.json)
- [10 sayfalık, yazdırılabilir PDF](pdf/typescript-1000.pdf)

Metot adları `.startsWith()` gibi kısa yazılmıştır. Üstlerindeki `String`, `Array` ve diğer başlıklar hangi nesneye ait olduklarını gösterir.

## Kapsam

İlk 100 madde TypeScript tür araçları ve sözdizimi kalıplarıdır. Sonraki bölümler TypeScript ile kullanılan JavaScript, tarayıcı ve Node.js metotlarını içerir. Bunlar TypeScript'e özgü 1.000 metot değildir.

`[statik]` işaretli metotlar sınıf üzerinde çağrılır. Parantezlerde gerekli argümanlar gösterilmez. Bazı API'ler uygun çalışma ortamı, izin veya güncel sürüm gerektirir.

## Günlük çalışma

Günde 10 madde seç, her biri için küçük bir örnek yaz ve ertesi gün önceki maddeleri tekrar et. Her bölümde 100 madde bulunur.

PDF için **A4, yatay, sayfaya sığdır** seç.

## JSON yapısı

`entries` dizisindeki her kayıt: `id`, `section`, `section_title`, `group`, `name`, `description_tr`, `kind`.

## Kaynaklar

- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/)
- [JavaScript ve Web API referansı](https://developer.mozilla.org/)
- [Node.js API referansı](https://nodejs.org/api/)
