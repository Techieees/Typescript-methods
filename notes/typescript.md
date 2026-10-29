# Typescript çalışma notları

1.000 madde · Türkçe açıklamalar · 10 bölüm

Her bölüm 100 madde içerir. Başlık veri türünü, nesneyi veya modülü belirtir. `()` içinde gerekli argümanlar gösterilmez.

İlk bölüm TypeScript tür ve sözdizimi kalıplarıdır. Diğer bölümler JavaScript, tarayıcı ve Node.js API’leridir. `[statik]` işaretli çağrılar sınıf üzerinde kullanılır.

## Bölümler

- [Bölüm 01: TypeScript: türler, bildirimler ve kalıplar](#bolum-01)
- [Bölüm 02: JavaScript: metinler, diziler ve türlenmiş diziler](#bolum-02)
- [Bölüm 03: JavaScript: nesneler, koleksiyonlar ve matematik](#bolum-03)
- [Bölüm 04: JavaScript: tarih, uluslararasılaştırma ve desenler](#bolum-04)
- [Bölüm 05: Asenkron işlemler, ağ ve akış API'leri](#bolum-05)
- [Bölüm 06: Tarayıcı: DOM, belge ve HTML öğeleri](#bolum-06)
- [Bölüm 07: Tarayıcı: Canvas, çizim ve görseller](#bolum-07)
- [Bölüm 08: Tarayıcı: depolama, performans ve iletişim](#bolum-08)
- [Bölüm 09: Node.js: dosyalar, yollar ve işletim sistemi](#bolum-09)
- [Bölüm 10: Node.js: Buffer, kriptografi ve olaylar](#bolum-10)

<a id="bolum-01"></a>
## Bölüm 01: TypeScript: türler, bildirimler ve kalıplar


### Temel türler

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 1 | `string` | Metin değerlerinin türüdür. |
| 2 | `number` | JavaScript sayı türünü belirtir. |
| 3 | `boolean` | true veya false türüdür. |
| 4 | `bigint` | Büyük tamsayı değerlerinin türüdür. |
| 5 | `symbol` | Benzersiz sembol değerlerinin türüdür. |
| 6 | `null` | Boş değer türünü belirtir. |
| 7 | `undefined` | Tanımsız değer türünü belirtir. |
| 8 | `void` | İşlev dönüşünün kullanılmadığını belirtir. |
| 9 | `never` | Oluşamayacak değer veya dönüşü belirtir. |
| 10 | `unknown` | Kullanmadan önce daraltılması gereken türdür. |
| 11 | `any` | Çoğu statik tür denetimini devre dışı bırakır. |
| 12 | `object` | İlkel olmayan değerleri temsil eder. |

### Diziler ve demetler

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 13 | `string[]` | Metin dizisi türünü tanımlar. |
| 14 | `Array<T>` | Genel dizi türünü tanımlar. |
| 15 | `ReadonlyArray<T>` | Salt okunur dizi görünümü tanımlar. |
| 16 | `[string, number]` | Sabit konumlu demet türü tanımlar. |
| 17 | `readonly [T, U]` | Salt okunur demet türü tanımlar. |
| 18 | `[x: number, y: number]` | Adlandırılmış demet alanları tanımlar. |
| 19 | `[T, U?]` | İsteğe bağlı demet öğesi tanımlar. |
| 20 | `[T, ...U[]]` | Değişken uzunluklu demet kuyruğu tanımlar. |

### Tür ve yapı bildirimleri

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 21 | `type Name = T` | Tür takma adı oluşturur. |
| 22 | `interface Name {}` | Nesne yapısını tanımlar. |
| 23 | `interface A extends B` | Arayüzü başka arayüzden genişletir. |
| 24 | `class A implements B` | Sınıfın arayüzü sağladığını denetler. |
| 25 | `A &#124; B` | Birleşim türü oluşturur. |
| 26 | `A & B` | Kesişim türü oluşturur. |
| 27 | `"open" &#124; "closed"` | Değişmez metinlerden birleşim oluşturur. |

### Tür işleçleri ve eşlemeler

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 28 | `keyof T` | Türün anahtarlarından birleşim oluşturur. |
| 29 | `typeof value` | Değerin türünü tür konumunda alır. |
| 30 | `T[K]` | Özelliğin türüne indisle erişir. |
| 31 | `T[number]` | Dizi veya demetin öğe türünü çıkarır. |
| 32 | `T extends U ? X : Y` | Koşullu tür seçimi yapar. |
| 33 | `infer R` | Koşullu türde ara türü çıkarır. |
| 34 | `{ [K in keyof T]: T[K] }` | Özellikleri eşleyerek yeni tür üretir. |
| 35 | `{ [K in keyof T]?: T[K] }` | Özellikleri isteğe bağlı yapar. |
| 36 | `{ [K in keyof T]-?: T[K] }` | İsteğe bağlılık işaretini kaldırır. |
| 37 | `{ readonly [K in keyof T]: T[K] }` | Eşlenen özellikleri salt okunur yapar. |
| 38 | `{ -readonly [K in keyof T]: T[K] }` | Salt okunurluk işaretini kaldırır. |
| 39 | `{ [K in keyof T as K]: T[K] }` | Eşlenen türde anahtar dönüşümü tanımlar. |
| 40 | ``prefix_${string}`` | Şablon metin türü oluşturur. |

### Hazır yardımcı türler

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 41 | `Partial<T>` | Bütün özellikleri isteğe bağlı yapar. |
| 42 | `Required<T>` | Bütün özellikleri zorunlu yapar. |
| 43 | `Readonly<T>` | Özelliklerin yeniden atanmasını engeller. |
| 44 | `Record<K, V>` | K anahtarları ve V değerleriyle tür kurar. |
| 45 | `Pick<T, K>` | Seçili özellikleri tutar. |
| 46 | `Omit<T, K>` | Seçili özellikleri kaldırır. |
| 47 | `Exclude<T, U>` | Birleşimden U ile uyumlu üyeleri çıkarır. |
| 48 | `Extract<T, U>` | Birleşimin U ile uyumlu üyelerini tutar. |
| 49 | `NonNullable<T>` | null ve undefined üyelerini kaldırır. |
| 50 | `Parameters<F>` | İşlev parametre türlerini demet yapar. |
| 51 | `ConstructorParameters<C>` | Kurucu parametrelerini demet yapar. |
| 52 | `ReturnType<F>` | İşlevin dönüş türünü çıkarır. |
| 53 | `InstanceType<C>` | Kurucunun örnek türünü çıkarır. |
| 54 | `ThisParameterType<F>` | Açık this parametresinin türünü çıkarır. |
| 55 | `OmitThisParameter<F>` | İşlev türünden this parametresini kaldırır. |
| 56 | `ThisType<T>` | Nesne yöntemleri için bağlamsal this belirtir. |
| 57 | `Awaited<T>` | Promise içindeki sonuç türünü açar. |
| 58 | `Uppercase<S>` | Metin türündeki harfleri büyütür. |
| 59 | `Lowercase<S>` | Metin türündeki harfleri küçültür. |
| 60 | `Capitalize<S>` | Metin türünün ilk harfini büyütür. |
| 61 | `Uncapitalize<S>` | Metin türünün ilk harfini küçültür. |
| 62 | `NoInfer<T>` | T konumundan tür çıkarımını engeller. |

### Daraltma ve işlev türleri

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 63 | `value as T` | Değeri belirtilen tür gibi ele alır. |
| 64 | `value satisfies T` | Uyumluluğu denetler, çıkarılan türü korur. |
| 65 | `value as const` | Sabit değişmez türler çıkarır. |
| 66 | `value!` | null ve undefined olasılığını türden çıkarır. |
| 67 | `prop?: T` | İsteğe bağlı özellik tanımlar. |
| 68 | `readonly prop: T` | Özelliğe yeniden atamayı engeller. |
| 69 | `[key: string]: T` | Metin anahtarlı indis imzası tanımlar. |
| 70 | `<T>` | Genel tür parametresi tanımlar. |
| 71 | `<T extends U>` | Genel türe üst kısıt koyar. |
| 72 | `<T = string>` | Varsayılan genel tür belirler. |
| 73 | `<const T>` | Genel parametrede değişmez tür çıkarımı ister. |
| 74 | `function f(x: T): U` | Parametre ve dönüş türünü belirtir. |
| 75 | `(x: T) => U` | İşlev türü tanımlar. |
| 76 | `new (...args: A) => T` | Kurucu imzası tanımlar. |
| 77 | `arg is T` | Tür daraltan yüklem tanımlar. |
| 78 | `asserts arg is T` | Başarılı çağrıdan sonra türü daraltır. |
| 79 | `asserts condition` | Başarılı çağrıdan sonra koşulu doğrular. |

### Sınıflar ve modül bildirimleri

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 80 | `function f(x: string): string;` | Tek uygulamaya ek çağrı imzası bildirir. |
| 81 | `abstract class A` | Doğrudan örneklenemeyen temel sınıf kurar. |
| 82 | `abstract method(): T` | Alt sınıfın uygulayacağı metodu bildirir. |
| 83 | `public member` | Herkese açık sınıf üyesi tanımlar. |
| 84 | `private member` | TS denetiminde özel sınıf üyesi tanımlar. |
| 85 | `protected member` | Sınıf ve alt sınıflara erişim verir. |
| 86 | `static member` | Üyeyi örnek yerine sınıfa bağlar. |
| 87 | `override method()` | Temel sınıf üyesini geçersiz kılmayı doğrular. |
| 88 | `constructor(public x: T)` | Kurucu parametresinden özellik oluşturur. |
| 89 | `get value(): T` | Okuma erişimcisi tanımlar. |
| 90 | `set value(v: T)` | Yazma erişimcisi tanımlar. |
| 91 | `enum E { A, B }` | Adlandırılmış sabit değerler grubu kurar. |
| 92 | `const enum E { A, B }` | Genellikle kullanımda satır içi enum üretir. |
| 93 | `declare const x: T` | Mevcut çalışma zamanı değerini bildirir. |
| 94 | `declare module "pkg"` | Modül tür bildirimini tanımlar veya genişletir. |
| 95 | `declare global {}` | Genel tür kapsamını genişletir. |
| 96 | `import type { T } from "pkg"` | Yalnızca tür amaçlı içe aktarır. |
| 97 | `export type { T }` | Türü dışa aktarır. |
| 98 | `import("pkg").T` | İçe aktarma türüyle üyeye erişir. |
| 99 | `namespace N {}` | Ad alanı oluşturur. |
| 100 | `unique symbol` | Tekil sembol kimliğini türde korur. |

<a id="bolum-02"></a>
## Bölüm 02: JavaScript: metinler, diziler ve türlenmiş diziler


### String

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 101 | `.fromCharCode() [statik]` | UTF-16 kod birimlerinden metin üretir. |
| 102 | `.fromCodePoint() [statik]` | Unicode kod noktalarından metin üretir. |
| 103 | `.raw() [statik]` | Şablonun ham metin parçalarını kullanır. |
| 104 | `.at()` | Konumdaki UTF-16 birimini getirir. |
| 105 | `.charAt()` | Konumdaki karakteri getirir. |
| 106 | `.charCodeAt()` | Konumdaki UTF-16 kodunu verir. |
| 107 | `.codePointAt()` | Konumdaki Unicode kod noktasını verir. |
| 108 | `.concat()` | Metinleri birleştirir. |
| 109 | `.endsWith()` | Belirtilen son ekle bitiyor mu? |
| 110 | `.includes()` | Alt metni içeriyor mu? |
| 111 | `.indexOf()` | İlk eşleşme konumunu verir. |
| 112 | `.lastIndexOf()` | Son eşleşme konumunu verir. |
| 113 | `.localeCompare()` | Yerel kurallarla karşılaştırır. |
| 114 | `.match()` | Düzenli ifadeyle eşleşmeleri alır. |
| 115 | `.matchAll()` | Eşleşmeleri yineleyici olarak verir. |
| 116 | `.normalize()` | Unicode normalleştirmesi yapar. |
| 117 | `.padEnd()` | Sonuna dolgu ekleyerek uzatır. |
| 118 | `.padStart()` | Başına dolgu ekleyerek uzatır. |
| 119 | `.repeat()` | Metni belirtilen sayıda tekrarlar. |
| 120 | `.replace()` | İlk veya desene bağlı eşleşmeleri değiştirir. |
| 121 | `.replaceAll()` | Bütün eşleşmeleri değiştirir. |
| 122 | `.search()` | Düzenli ifadenin ilk konumunu bulur. |
| 123 | `.slice()` | Metnin bir bölümünü kopyalar. |
| 124 | `.split()` | Ayırıcıya göre dizi oluşturur. |
| 125 | `.startsWith()` | Belirtilen başlangıçla başlıyor mu? |
| 126 | `.substring()` | İki indis arasındaki metni alır. |
| 127 | `.toLocaleLowerCase()` | Yerel kurallarla harfleri küçültür. |
| 128 | `.toLocaleUpperCase()` | Yerel kurallarla harfleri büyütür. |
| 129 | `.toLowerCase()` | Harfleri küçültür. |
| 130 | `.toUpperCase()` | Harfleri büyütür. |
| 131 | `.trim()` | İki uçtaki boşlukları kaldırır. |
| 132 | `.trimEnd()` | Sondaki boşlukları kaldırır. |
| 133 | `.trimStart()` | Baştaki boşlukları kaldırır. |
| 134 | `.toString()` | Metin değerini döndürür. |
| 135 | `.valueOf()` | İlkel metin değerini döndürür. |

### Array

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 136 | `.from() [statik]` | Yinelenebilir veya dizi benzerinden dizi kurar. |
| 137 | `.fromAsync() [statik]` | Asenkron kaynaktan Promise ile dizi üretir. |
| 138 | `.isArray() [statik]` | Değerin dizi olduğunu kontrol eder. |
| 139 | `.of() [statik]` | Argümanlardan dizi oluşturur. |
| 140 | `.at()` | Negatif indis de destekleyerek öğe alır. |
| 141 | `.concat()` | Dizileri yeni dizide birleştirir. |
| 142 | `.copyWithin()` | Öğeleri dizi içinde kopyalar. |
| 143 | `.entries()` | İndis ve değer çiftlerini yineler. |
| 144 | `.every()` | Bütün öğeler koşulu sağlıyor mu? |
| 145 | `.fill()` | Diziyi verilen değerle doldurur. |
| 146 | `.filter()` | Koşulu sağlayan öğeleri seçer. |
| 147 | `.find()` | Koşulu sağlayan ilk öğeyi bulur. |
| 148 | `.findIndex()` | Koşulu sağlayan ilk indisi bulur. |
| 149 | `.findLast()` | Koşulu sağlayan son öğeyi bulur. |
| 150 | `.findLastIndex()` | Koşulu sağlayan son indisi bulur. |
| 151 | `.flat()` | İç içe dizileri düzleştirir. |
| 152 | `.flatMap()` | Eşler ve bir düzey düzleştirir. |
| 153 | `.forEach()` | Her öğe için işlev çalıştırır. |
| 154 | `.includes()` | Öğenin varlığını kontrol eder. |
| 155 | `.indexOf()` | Öğenin ilk konumunu bulur. |
| 156 | `.join()` | Öğeleri ayırıcıyla metne çevirir. |
| 157 | `.keys()` | Dizi indislerini yineler. |
| 158 | `.lastIndexOf()` | Öğenin son konumunu bulur. |
| 159 | `.map()` | Öğeleri dönüştürüp yeni dizi üretir. |
| 160 | `.pop()` | Son öğeyi çıkarıp döndürür. |
| 161 | `.push()` | Sona öğe ekler; yeni uzunluğu verir. |
| 162 | `.reduce()` | Soldan birikimli sonuç hesaplar. |
| 163 | `.reduceRight()` | Sağdan birikimli sonuç hesaplar. |
| 164 | `.reverse()` | Öğe sırasını yerinde tersine çevirir. |
| 165 | `.shift()` | İlk öğeyi çıkarıp döndürür. |
| 166 | `.slice()` | Dizinin bölümünü kopyalar. |
| 167 | `.some()` | En az bir öğe koşulu sağlıyor mu? |
| 168 | `.sort()` | Diziyi yerinde sıralar. |
| 169 | `.splice()` | Aradan öğe siler, değiştirir veya ekler. |
| 170 | `.toLocaleString()` | Öğeleri yerel kurallarla metne çevirir. |
| 171 | `.toReversed()` | Ters sıralı yeni dizi üretir. |
| 172 | `.toSorted()` | Sıralanmış yeni dizi üretir. |
| 173 | `.toSpliced()` | Kesme ve eklemeyi yeni diziye uygular. |
| 174 | `.toString()` | Diziyi metne dönüştürür. |
| 175 | `.unshift()` | Başa öğe ekler; yeni uzunluğu verir. |
| 176 | `.values()` | Dizi değerlerini yineler. |
| 177 | `.with()` | Tek konumu değiştirilmiş kopya üretir. |

### Uint8Array

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 178 | `.from() [statik]` | Kaynaktan sekiz bitlik dizi oluşturur. |
| 179 | `.of() [statik]` | Argümanlardan sekiz bitlik dizi kurar. |
| 180 | `.set()` | Başka dizinin değerlerini kopyalar. |
| 181 | `.subarray()` | Aynı bellekte alt dizi görünümü verir. |
| 182 | `.slice()` | Dizi bölümünün kopyasını üretir. |
| 183 | `.at()` | Konumdaki sayısal öğeyi alır. |
| 184 | `.copyWithin()` | Değerleri aynı dizi içinde kopyalar. |
| 185 | `.entries()` | İndis ve değer çiftlerini yineler. |
| 186 | `.every()` | Bütün sayılar koşulu sağlıyor mu? |
| 187 | `.fill()` | Diziyi sayısal değerle doldurur. |
| 188 | `.filter()` | Koşulu sağlayan sayıları seçer. |
| 189 | `.find()` | Koşulu sağlayan ilk sayıyı bulur. |
| 190 | `.findIndex()` | Koşulu sağlayan ilk indisi bulur. |
| 191 | `.forEach()` | Her sayı için işlev çalıştırır. |
| 192 | `.includes()` | Sayının dizide varlığını sınar. |
| 193 | `.indexOf()` | Sayının ilk konumunu bulur. |
| 194 | `.join()` | Sayıları ayırıcıyla metne çevirir. |
| 195 | `.keys()` | Sayısal dizinin indislerini yineler. |
| 196 | `.lastIndexOf()` | Sayının son konumunu bulur. |
| 197 | `.map()` | Sayıları yeni türlenmiş diziye eşler. |
| 198 | `.reduce()` | Sayıları tek bir sonuçta biriktirir. |
| 199 | `.reduceRight()` | Sayıları sağdan biriktirir. |
| 200 | `.reverse()` | Sayısal diziyi yerinde ters çevirir. |

<a id="bolum-03"></a>
## Bölüm 03: JavaScript: nesneler, koleksiyonlar ve matematik


### Object

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 201 | `.assign() [statik]` | Kaynakların kendi sayılabilir alanlarını kopyalar. |
| 202 | `.create() [statik]` | Belirtilen prototiple nesne oluşturur. |
| 203 | `.defineProperty() [statik]` | Bir özelliğin tanımını ayarlar. |
| 204 | `.defineProperties() [statik]` | Birden fazla özelliğin tanımını ayarlar. |
| 205 | `.entries() [statik]` | Kendi sayılabilir anahtar-değer çiftlerini verir. |
| 206 | `.fromEntries() [statik]` | Anahtar-değer çiftlerinden nesne kurar. |
| 207 | `.freeze() [statik]` | Nesnenin doğrudan özelliklerini dondurur. |
| 208 | `.getOwnPropertyDescriptor() [statik]` | Bir özelliğin tanımını getirir. |
| 209 | `.getOwnPropertyDescriptors() [statik]` | Kendi özellik tanımlarını getirir. |
| 210 | `.getOwnPropertyNames() [statik]` | Kendi metin özellik adlarını getirir. |
| 211 | `.getOwnPropertySymbols() [statik]` | Kendi sembol anahtarlarını getirir. |
| 212 | `.getPrototypeOf() [statik]` | Nesnenin prototipini getirir. |
| 213 | `.hasOwn() [statik]` | Özellik doğrudan nesneye mi ait? |
| 214 | `.is() [statik]` | Aynı değer karşılaştırması yapar. |
| 215 | `.isExtensible() [statik]` | Yeni özellik eklenebilir mi? |
| 216 | `.isFrozen() [statik]` | Nesne dondurulmuş mu? |
| 217 | `.isSealed() [statik]` | Nesne mühürlenmiş mi? |
| 218 | `.keys() [statik]` | Kendi sayılabilir metin anahtarlarını verir. |
| 219 | `.preventExtensions() [statik]` | Yeni özellik eklenmesini engeller. |
| 220 | `.seal() [statik]` | Özellik ekleme ve silmeyi engeller. |
| 221 | `.setPrototypeOf() [statik]` | Nesnenin prototipini değiştirir. |
| 222 | `.values() [statik]` | Kendi sayılabilir özellik değerlerini verir. |

### Reflect

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 223 | `.apply()` | İşlevi this ve argüman listesiyle çağırır. |
| 224 | `.construct()` | Kurucuyu argüman listesiyle çağırır. |
| 225 | `.defineProperty()` | Özellik tanımlar; başarı bilgisi döndürür. |
| 226 | `.deleteProperty()` | Özelliği siler; başarı bilgisi döndürür. |
| 227 | `.get()` | Nesne özelliğini getirir. |
| 228 | `.getOwnPropertyDescriptor()` | Kendi özellik tanımını getirir. |
| 229 | `.getPrototypeOf()` | Prototipi getirir. |
| 230 | `.has()` | Prototip zinciri dahil özellik var mı? |
| 231 | `.isExtensible()` | Nesne genişletilebilir mi? |
| 232 | `.ownKeys()` | Bütün kendi anahtarlarını getirir. |
| 233 | `.preventExtensions()` | Genişletmeyi engeller; başarıyı bildirir. |
| 234 | `.set()` | Özelliğe değer atar. |
| 235 | `.setPrototypeOf()` | Prototipi atar; başarıyı bildirir. |

### Map

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 236 | `.clear()` | Bütün anahtar-değer çiftlerini kaldırır. |
| 237 | `.delete()` | Anahtarı ve değerini siler. |
| 238 | `.entries()` | Anahtar-değer çiftlerini yineler. |
| 239 | `.forEach()` | Her çift için işlev çalıştırır. |
| 240 | `.get()` | Anahtarın değerini getirir. |
| 241 | `.has()` | Anahtar mevcut mu? |
| 242 | `.keys()` | Anahtarları yineler. |
| 243 | `.set()` | Anahtara değer atar. |
| 244 | `.values()` | Değerleri yineler. |

### Set

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 245 | `.add()` | Kümeye değer ekler. |
| 246 | `.clear()` | Kümeyi boşaltır. |
| 247 | `.delete()` | Değeri kümeden siler. |
| 248 | `.entries()` | Değer-değer çiftlerini yineler. |
| 249 | `.forEach()` | Her değer için işlev çalıştırır. |
| 250 | `.has()` | Değer kümede mevcut mu? |
| 251 | `.keys()` | Kümenin değerlerini yineler. |
| 252 | `.values()` | Kümenin değerlerini yineler. |

### WeakMap

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 253 | `.delete()` | Zayıf anahtar eşlemesini siler. |
| 254 | `.get()` | Zayıf anahtarın değerini getirir. |
| 255 | `.has()` | Zayıf anahtar mevcut mu? |
| 256 | `.set()` | Zayıf anahtara değer atar. |

### WeakSet

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 257 | `.add()` | Zayıf kümeye değer ekler. |
| 258 | `.delete()` | Değeri zayıf kümeden siler. |
| 259 | `.has()` | Değer zayıf kümede mevcut mu? |

### Math

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 260 | `.abs()` | Mutlak değer hesaplar. |
| 261 | `.acos()` | Ters kosinüs hesaplar. |
| 262 | `.acosh()` | Ters hiperbolik kosinüs hesaplar. |
| 263 | `.asin()` | Ters sinüs hesaplar. |
| 264 | `.asinh()` | Ters hiperbolik sinüs hesaplar. |
| 265 | `.atan()` | Ters tanjant hesaplar. |
| 266 | `.atanh()` | Ters hiperbolik tanjant hesaplar. |
| 267 | `.atan2()` | Koordinatların yön açısını hesaplar. |
| 268 | `.cbrt()` | Küpkök hesaplar. |
| 269 | `.ceil()` | Yukarı tamsayıya yuvarlar. |
| 270 | `.clz32()` | Otuz iki bitte baştaki sıfırları sayar. |
| 271 | `.cos()` | Radyan cinsinden kosinüs hesaplar. |
| 272 | `.cosh()` | Hiperbolik kosinüs hesaplar. |
| 273 | `.exp()` | e üzeri x hesaplar. |
| 274 | `.expm1()` | e üzeri x eksi bir hesaplar. |
| 275 | `.floor()` | Aşağı tamsayıya yuvarlar. |
| 276 | `.fround()` | Otuz iki bit kayan sayıya yuvarlar. |
| 277 | `.hypot()` | Kareler toplamının karekökünü alır. |
| 278 | `.imul()` | Otuz iki bit tamsayı çarpımı yapar. |
| 279 | `.log()` | Doğal logaritma hesaplar. |
| 280 | `.log1p()` | Bir artı x'in logaritmasını hesaplar. |
| 281 | `.log10()` | On tabanında logaritma hesaplar. |
| 282 | `.log2()` | İki tabanında logaritma hesaplar. |
| 283 | `.max()` | En büyük sayıyı verir. |
| 284 | `.min()` | En küçük sayıyı verir. |
| 285 | `.pow()` | Üs alma işlemi yapar. |
| 286 | `.random()` | Sıfır dahil, bir hariç rastgele sayı verir. |
| 287 | `.round()` | En yakın tamsayıya yuvarlar. |
| 288 | `.sign()` | Sayının işaretini verir. |
| 289 | `.sin()` | Radyan cinsinden sinüs hesaplar. |
| 290 | `.sinh()` | Hiperbolik sinüs hesaplar. |
| 291 | `.sqrt()` | Karekök hesaplar. |
| 292 | `.tan()` | Radyan cinsinden tanjant hesaplar. |
| 293 | `.tanh()` | Hiperbolik tanjant hesaplar. |
| 294 | `.trunc()` | Kesirli kısmı atar. |

### Number

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 295 | `.isFinite() [statik]` | Değer sonlu number mı? |
| 296 | `.isInteger() [statik]` | Değer tamsayı mı? |
| 297 | `.isNaN() [statik]` | Değer NaN mı? |
| 298 | `.isSafeInteger() [statik]` | Güvenli tamsayı aralığında mı? |
| 299 | `.parseFloat() [statik]` | Metnin başından ondalıklı sayı okur. |
| 300 | `.parseInt() [statik]` | Metnin başından tamsayı okur. |

<a id="bolum-04"></a>
## Bölüm 04: JavaScript: tarih, uluslararasılaştırma ve desenler


### Date

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 301 | `.now() [statik]` | Geçerli zamanı milisaniye damgası verir. |
| 302 | `.parse() [statik]` | Tarih metnini zaman damgasına çevirir. |
| 303 | `.UTC() [statik]` | UTC bileşenlerinden zaman damgası üretir. |
| 304 | `.getDate()` | Yerel ayın gününü verir. |
| 305 | `.getDay()` | Yerel hafta gününü pazar sıfırla verir. |
| 306 | `.getFullYear()` | Yerel yılı verir. |
| 307 | `.getHours()` | Yerel saati verir. |
| 308 | `.getMilliseconds()` | Yerel milisaniye alanını verir. |
| 309 | `.getMinutes()` | Yerel dakika alanını verir. |
| 310 | `.getMonth()` | Yerel ayı sıfır tabanlı verir. |
| 311 | `.getSeconds()` | Yerel saniye alanını verir. |
| 312 | `.getTime()` | Milisaniye zaman damgasını verir. |
| 313 | `.getTimezoneOffset()` | UTC eksi yerel farkını dakika verir. |
| 314 | `.getUTCDate()` | UTC ayın gününü verir. |
| 315 | `.getUTCDay()` | UTC hafta gününü verir. |
| 316 | `.getUTCFullYear()` | UTC yılını verir. |
| 317 | `.getUTCHours()` | UTC saatini verir. |
| 318 | `.getUTCMilliseconds()` | UTC milisaniye alanını verir. |
| 319 | `.getUTCMinutes()` | UTC dakika alanını verir. |
| 320 | `.getUTCMonth()` | UTC ayını sıfır tabanlı verir. |
| 321 | `.getUTCSeconds()` | UTC saniye alanını verir. |
| 322 | `.setDate()` | Yerel ayın gününü değiştirir. |
| 323 | `.setFullYear()` | Yerel yılı değiştirir. |
| 324 | `.setHours()` | Yerel saat bileşenlerini değiştirir. |
| 325 | `.setMilliseconds()` | Yerel milisaniyeyi değiştirir. |
| 326 | `.setMinutes()` | Yerel dakikayı değiştirir. |
| 327 | `.setMonth()` | Yerel ayı değiştirir. |
| 328 | `.setSeconds()` | Yerel saniyeyi değiştirir. |
| 329 | `.setTime()` | Milisaniye damgasını değiştirir. |
| 330 | `.setUTCDate()` | UTC ayın gününü değiştirir. |
| 331 | `.setUTCFullYear()` | UTC yılını değiştirir. |
| 332 | `.setUTCHours()` | UTC saat bileşenlerini değiştirir. |
| 333 | `.setUTCMilliseconds()` | UTC milisaniyeyi değiştirir. |
| 334 | `.setUTCMinutes()` | UTC dakikayı değiştirir. |
| 335 | `.setUTCMonth()` | UTC ayı değiştirir. |
| 336 | `.setUTCSeconds()` | UTC saniyeyi değiştirir. |
| 337 | `.toDateString()` | Yerel tarih metni üretir. |
| 338 | `.toISOString()` | UTC ISO tarih ve saat metni üretir. |
| 339 | `.toJSON()` | JSON için tarih metni üretir. |
| 340 | `.toLocaleDateString()` | Yerel kurallarla tarihi biçimler. |
| 341 | `.toLocaleString()` | Yerel kurallarla tarih ve saati biçimler. |
| 342 | `.toLocaleTimeString()` | Yerel kurallarla saati biçimler. |
| 343 | `.toString()` | Yerel tarih ve saati metne çevirir. |
| 344 | `.toTimeString()` | Yerel saat metni üretir. |
| 345 | `.toUTCString()` | UTC tarih ve saat metni üretir. |
| 346 | `.valueOf()` | Milisaniye damgasını ilkel değer verir. |

### Intl

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 347 | `.getCanonicalLocales() [statik]` | Dil etiketlerini standartlaştırır. |
| 348 | `.supportedValuesOf() [statik]` | Desteklenen uluslararası değerleri listeler. |

### Intl · biçimleyici örnekleri / statik

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 349 | `.Collator.supportedLocalesOf() [statik]` | Desteklenen karşılaştırma dillerini bulur. |
| 350 | `.Collator.compare()` | Yerel kurallarla iki metni karşılaştırır. |
| 351 | `.Collator.resolvedOptions()` | Etkin karşılaştırma seçeneklerini verir. |
| 352 | `.DateTimeFormat.supportedLocalesOf() [statik]` | Desteklenen tarih biçim dillerini bulur. |
| 353 | `.DateTimeFormat.format()` | Tarih ve saati yerel biçimde yazar. |
| 354 | `.DateTimeFormat.formatToParts()` | Tarih çıktısını anlamlı parçalara böler. |
| 355 | `.DateTimeFormat.formatRange()` | Tarih aralığını yerel biçimde yazar. |
| 356 | `.DateTimeFormat.formatRangeToParts()` | Tarih aralığını parçalara ayırır. |
| 357 | `.DateTimeFormat.resolvedOptions()` | Etkin tarih biçim seçeneklerini verir. |
| 358 | `.NumberFormat.supportedLocalesOf() [statik]` | Desteklenen sayı biçim dillerini bulur. |
| 359 | `.NumberFormat.format()` | Sayıyı yerel kurallarla biçimler. |
| 360 | `.NumberFormat.formatToParts()` | Sayı çıktısını anlamlı parçalara ayırır. |
| 361 | `.NumberFormat.formatRange()` | Sayı aralığını yerel biçimde yazar. |
| 362 | `.NumberFormat.formatRangeToParts()` | Sayı aralığını parçalara ayırır. |
| 363 | `.NumberFormat.resolvedOptions()` | Etkin sayı biçim seçeneklerini verir. |
| 364 | `.PluralRules.supportedLocalesOf() [statik]` | Desteklenen çoğul kuralı dillerini bulur. |
| 365 | `.PluralRules.select()` | Sayının çoğul kategorisini seçer. |
| 366 | `.PluralRules.selectRange()` | Sayı aralığının çoğul kategorisini seçer. |
| 367 | `.PluralRules.resolvedOptions()` | Etkin çoğul seçeneklerini verir. |
| 368 | `.RelativeTimeFormat.supportedLocalesOf() [statik]` | Desteklenen göreli zaman dillerini bulur. |
| 369 | `.RelativeTimeFormat.format()` | Göreli zaman ifadesi üretir. |
| 370 | `.RelativeTimeFormat.formatToParts()` | Göreli zaman çıktısını parçalara böler. |
| 371 | `.RelativeTimeFormat.resolvedOptions()` | Etkin göreli zaman seçeneklerini verir. |
| 372 | `.ListFormat.supportedLocalesOf() [statik]` | Desteklenen liste biçim dillerini bulur. |
| 373 | `.ListFormat.format()` | Metin listesini yerel kurallarla birleştirir. |
| 374 | `.ListFormat.formatToParts()` | Biçimli listeyi parçalara ayırır. |
| 375 | `.ListFormat.resolvedOptions()` | Etkin liste biçim seçeneklerini verir. |
| 376 | `.Segmenter.supportedLocalesOf() [statik]` | Desteklenen metin bölme dillerini bulur. |
| 377 | `.Segmenter.segment()` | Metni harf, sözcük veya cümleye böler. |
| 378 | `.Segmenter.resolvedOptions()` | Etkin bölümleme seçeneklerini verir. |
| 379 | `.DisplayNames.supportedLocalesOf() [statik]` | Desteklenen adlandırma dillerini bulur. |
| 380 | `.DisplayNames.of()` | Dil, bölge veya para biriminin adını verir. |
| 381 | `.DisplayNames.resolvedOptions()` | Etkin adlandırma seçeneklerini verir. |

### RegExp

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 382 | `.exec()` | Eşleşme ayrıntılarını veya null verir. |
| 383 | `.test()` | Desenin eşleşip eşleşmediğini sınar. |
| 384 | `.toString()` | Deseni ve bayraklarını metne çevirir. |

### JSON

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 385 | `.parse()` | JSON metnini JavaScript değerine çevirir. |
| 386 | `.stringify()` | Değeri JSON metnine dönüştürür. |

### BigInt

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 387 | `.asIntN() [statik]` | BigInt değerini işaretli bit genişliğine sarar. |
| 388 | `.asUintN() [statik]` | BigInt değerini işaretsiz bit genişliğine sarar. |
| 389 | `.toString()` | Tamsayıyı seçilen tabanda metne çevirir. |
| 390 | `.toLocaleString()` | Büyük tamsayıyı yerel kurallarla biçimler. |
| 391 | `.valueOf()` | İlkel BigInt değerini verir. |

### Boolean

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 392 | `.toString()` | Mantıksal değeri metne çevirir. |
| 393 | `.valueOf()` | İlkel mantıksal değeri verir. |

### Symbol

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 394 | `.for() [statik]` | Genel sembol kaydından sembol alır. |
| 395 | `.keyFor() [statik]` | Genel sembolün kayıt anahtarını bulur. |
| 396 | `.toString()` | Sembolün okunabilir gösterimini verir. |
| 397 | `.valueOf()` | İlkel sembol değerini verir. |

### Function

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 398 | `.apply()` | İşlevi this ve argüman dizisiyle çağırır. |
| 399 | `.bind()` | this ve bazı argümanları bağlar. |
| 400 | `.call()` | İşlevi açık this değeriyle çağırır. |

<a id="bolum-05"></a>
## Bölüm 05: Asenkron işlemler, ağ ve akış API'leri


### Promise

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 401 | `.all() [statik]` | Bütün sonuçları bekler; ilk hatada reddeder. |
| 402 | `.allSettled() [statik]` | Başarı ve hata sonuçlarının hepsini bekler. |
| 403 | `.any() [statik]` | İlk başarılı sonucu bekler. |
| 404 | `.race() [statik]` | İlk sonuçlanan Promise'i izler. |
| 405 | `.resolve() [statik]` | Değeri çözümlenen Promise'e dönüştürür. |
| 406 | `.reject() [statik]` | Reddedilmiş Promise oluşturur. |
| 407 | `.withResolvers() [statik]` | Promise ve çözümleme işlevlerini verir. |
| 408 | `.then()` | Başarı veya hata işleyicisi ekler. |
| 409 | `.catch()` | Reddedilme işleyicisi ekler. |
| 410 | `.finally()` | Sonuçtan bağımsız son işlem ekler. |

### Genel işlevler

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 411 | `fetch()` | HTTP isteği gönderip Response bekler. |
| 412 | `queueMicrotask()` | Mikro görev kuyruğuna iş ekler. |
| 413 | `setTimeout()` | Gecikmeden sonra görev planlar. |
| 414 | `clearTimeout()` | Zaman aşımı görevini iptal eder. |
| 415 | `setInterval()` | Tekrarlanan görev planlar. |
| 416 | `clearInterval()` | Tekrarlanan görevi iptal eder. |
| 417 | `structuredClone()` | Desteklenen değerlerin derin kopyasını alır. |

### AbortController

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 418 | `.abort()` | Bağlı işlemlere iptal sinyali gönderir. |

### AbortSignal

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 419 | `.abort() [statik]` | Zaten iptal edilmiş sinyal oluşturur. |
| 420 | `.timeout() [statik]` | Süre sonunda iptal olan sinyal oluşturur. |
| 421 | `.any() [statik]` | İlk iptali izleyen birleşik sinyal üretir. |
| 422 | `.throwIfAborted()` | Sinyal iptalse nedenini fırlatır. |

### Fetch · Request / Response / Headers

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 423 | `.Request.arrayBuffer()` | İstek gövdesini ArrayBuffer olarak okur. |
| 424 | `.Request.blob()` | İstek gövdesini Blob olarak okur. |
| 425 | `.Request.clone()` | İstek nesnesini kopyalar. |
| 426 | `.Request.formData()` | İstek gövdesini form verisi olarak okur. |
| 427 | `.Request.json()` | İstek gövdesini JSON olarak çözer. |
| 428 | `.Request.text()` | İstek gövdesini metin olarak okur. |
| 429 | `.Response.error() [statik]` | Ağ hatasını temsil eden yanıt üretir. |
| 430 | `.Response.json() [statik]` | JSON gövdeli yanıt üretir. |
| 431 | `.Response.redirect() [statik]` | Yönlendirme yanıtı üretir. |
| 432 | `.Response.arrayBuffer()` | Yanıt gövdesini ArrayBuffer olarak okur. |
| 433 | `.Response.blob()` | Yanıt gövdesini Blob olarak okur. |
| 434 | `.Response.clone()` | Yanıt nesnesini kopyalar. |
| 435 | `.Response.formData()` | Yanıt gövdesini form verisi olarak okur. |
| 436 | `.Response.json()` | Yanıt gövdesini JSON olarak çözer. |
| 437 | `.Response.text()` | Yanıt gövdesini metin olarak okur. |
| 438 | `.Headers.append()` | Üstbilgiye ek değer ekler. |
| 439 | `.Headers.delete()` | Üstbilgiyi kaldırır. |
| 440 | `.Headers.entries()` | Üstbilgi çiftlerini yineler. |
| 441 | `.Headers.forEach()` | Her üstbilgi için işlev çalıştırır. |
| 442 | `.Headers.get()` | Üstbilgi değerini getirir. |
| 443 | `.Headers.has()` | Üstbilgi mevcut mu? |
| 444 | `.Headers.keys()` | Üstbilgi adlarını yineler. |
| 445 | `.Headers.set()` | Üstbilgi değerini değiştirir. |
| 446 | `.Headers.values()` | Üstbilgi değerlerini yineler. |

### FormData

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 447 | `.append()` | Forma alan veya dosya ekler. |
| 448 | `.delete()` | Adı verilen alanları kaldırır. |
| 449 | `.entries()` | Form alanı çiftlerini yineler. |
| 450 | `.forEach()` | Her form alanı için işlev çalıştırır. |
| 451 | `.get()` | Adın ilk değerini getirir. |
| 452 | `.getAll()` | Adın bütün değerlerini getirir. |
| 453 | `.has()` | Adı verilen alan mevcut mu? |
| 454 | `.keys()` | Alan adlarını yineler. |
| 455 | `.set()` | Alan değerlerini tek değerle değiştirir. |
| 456 | `.values()` | Alan değerlerini yineler. |

### URL

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 457 | `.canParse() [statik]` | Metin verilen tabanla URL olabilir mi? |
| 458 | `.createObjectURL() [statik]` | Blob için geçici nesne URL'si üretir. |
| 459 | `.revokeObjectURL() [statik]` | Nesne URL'sini serbest bırakır. |
| 460 | `.toJSON()` | URL'yi JSON için metne çevirir. |
| 461 | `.toString()` | URL'nin tam metnini verir. |

### URLSearchParams

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 462 | `.append()` | Sorguya anahtar-değer çifti ekler. |
| 463 | `.delete()` | Eşleşen sorgu parametresini siler. |
| 464 | `.entries()` | Parametre çiftlerini yineler. |
| 465 | `.forEach()` | Her parametre için işlev çalıştırır. |
| 466 | `.get()` | Parametrenin ilk değerini getirir. |
| 467 | `.getAll()` | Parametrenin bütün değerlerini getirir. |
| 468 | `.has()` | Parametrenin varlığını denetler. |
| 469 | `.keys()` | Parametre anahtarlarını yineler. |
| 470 | `.set()` | Parametrenin değerini ayarlar. |
| 471 | `.sort()` | Parametreleri anahtara göre sıralar. |
| 472 | `.toString()` | Kodlanmış sorgu metni üretir. |
| 473 | `.values()` | Parametre değerlerini yineler. |

### Blob

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 474 | `.arrayBuffer()` | Blob içeriğini ArrayBuffer olarak okur. |
| 475 | `.slice()` | Blob'un bir bölümünü alır. |
| 476 | `.stream()` | İçeriği okunabilir akış olarak verir. |
| 477 | `.text()` | İçeriği metin olarak okur. |

### Metin kodlama · TextEncoder / TextDecoder

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 478 | `.TextEncoder.encode()` | Metni UTF-8 baytlarına çevirir. |
| 479 | `.TextEncoder.encodeInto()` | UTF-8 baytlarını hedef diziye yazar. |
| 480 | `.TextDecoder.decode()` | Baytları metne dönüştürür. |

### Streams · akış nesneleri

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 481 | `.ReadableStream.cancel()` | Okunabilir akışı iptal eder. |
| 482 | `.ReadableStream.getReader()` | Akışa özel okuyucu alır. |
| 483 | `.ReadableStream.pipeThrough()` | Akışı dönüşüm üzerinden geçirir. |
| 484 | `.ReadableStream.pipeTo()` | Akışı yazılabilir hedefe aktarır. |
| 485 | `.ReadableStream.tee()` | Okunabilir akışı iki kola ayırır. |
| 486 | `.ReadReader.cancel()` | Okunan akışı iptal eder. |
| 487 | `.ReadReader.read()` | Sonraki veri parçasını bekler. |
| 488 | `.ReadReader.releaseLock()` | Okuyucunun akış kilidini bırakır. |
| 489 | `.WritableStream.abort()` | Yazılabilir akışı hatayla durdurur. |
| 490 | `.WritableStream.close()` | Yazılabilir akışı kapatır. |
| 491 | `.WritableStream.getWriter()` | Akışa özel yazıcı alır. |
| 492 | `.WriteWriter.abort()` | Yazılan akışı hatayla durdurur. |
| 493 | `.WriteWriter.close()` | Yazma işlemlerinden sonra kapatır. |
| 494 | `.WriteWriter.releaseLock()` | Yazıcının akış kilidini bırakır. |
| 495 | `.WriteWriter.write()` | Akışa veri parçası yazar. |
| 496 | `.TransformController.enqueue()` | Dönüşüm çıktısına parça ekler. |
| 497 | `.TransformController.error()` | Dönüşüm akışını hataya geçirir. |
| 498 | `.TransformController.terminate()` | Dönüşümü sonlandırır. |
| 499 | `.ReadController.close()` | Okunabilir akışı kapatır. |
| 500 | `.ReadController.enqueue()` | Okuma kuyruğuna veri ekler. |

<a id="bolum-06"></a>
## Bölüm 06: Tarayıcı: DOM, belge ve HTML öğeleri


### Document

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 501 | `.getElementById()` | Kimliği verilen öğeyi bulur. |
| 502 | `.getElementsByClassName()` | Sınıfa uyan canlı öğe koleksiyonu verir. |
| 503 | `.getElementsByTagName()` | Etiket adına göre canlı koleksiyon verir. |
| 504 | `.getElementsByName()` | name alanına göre canlı koleksiyon verir. |
| 505 | `.querySelector()` | CSS seçicisine uyan ilk öğeyi verir. |
| 506 | `.querySelectorAll()` | CSS seçicisine uyan sabit liste verir. |
| 507 | `.createElement()` | HTML öğesi oluşturur. |
| 508 | `.createElementNS()` | Ad alanıyla öğe oluşturur. |
| 509 | `.createTextNode()` | Metin düğümü oluşturur. |
| 510 | `.createComment()` | Yorum düğümü oluşturur. |
| 511 | `.createDocumentFragment()` | Geçici belge parçası oluşturur. |
| 512 | `.createAttribute()` | Öznitelik düğümü oluşturur. |
| 513 | `.createRange()` | Belge aralığı oluşturur. |
| 514 | `.createTreeWalker()` | Filtreli ağaç gezgini oluşturur. |
| 515 | `.createNodeIterator()` | Düğüm yineleyicisi oluşturur. |
| 516 | `.importNode()` | Başka belgedeki düğümü kopyalar. |
| 517 | `.adoptNode()` | Düğümü başka belgeden devralır. |
| 518 | `.elementFromPoint()` | Koordinattaki en üst öğeyi bulur. |
| 519 | `.elementsFromPoint()` | Koordinattaki öğeleri sırayla verir. |
| 520 | `.getSelection()` | Belgedeki metin seçimini getirir. |
| 521 | `.hasFocus()` | Belgenin odağı var mı? |
| 522 | `.exitFullscreen()` | Tam ekran modundan çıkar. |

### Node

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 523 | `.appendChild()` | Alt düğümü sona ekler veya taşır. |
| 524 | `.cloneNode()` | Düğümün kopyasını oluşturur. |
| 525 | `.compareDocumentPosition()` | Düğümlerin belge sırasını karşılaştırır. |
| 526 | `.contains()` | Düğümün alt ağacında bulunuyor mu? |
| 527 | `.getRootNode()` | Düğümün kökünü bulur. |
| 528 | `.hasChildNodes()` | Alt düğüm var mı? |
| 529 | `.insertBefore()` | Düğümü başka alt düğümün önüne ekler. |
| 530 | `.isEqualNode()` | Yapısal düğüm eşitliğini kontrol eder. |
| 531 | `.isSameNode()` | Aynı düğüm nesnesi mi? |
| 532 | `.normalize()` | Bitişik metin düğümlerini birleştirir. |
| 533 | `.removeChild()` | Alt düğümü çıkarır. |
| 534 | `.replaceChild()` | Alt düğümü başka düğümle değiştirir. |
| 535 | `.lookupNamespaceURI()` | Önekin ad alanı URI'sini bulur. |
| 536 | `.lookupPrefix()` | Ad alanının önekini bulur. |
| 537 | `.isDefaultNamespace()` | URI varsayılan ad alanı mı? |

### Element

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 538 | `.after()` | Öğenin arkasına içerik ekler. |
| 539 | `.before()` | Öğenin önüne içerik ekler. |
| 540 | `.append()` | İçeriği alt öğelerin sonuna ekler. |
| 541 | `.prepend()` | İçeriği alt öğelerin başına ekler. |
| 542 | `.remove()` | Öğeyi belgeden kaldırır. |
| 543 | `.replaceWith()` | Öğeyi verilen içerikle değiştirir. |
| 544 | `.replaceChildren()` | Bütün alt düğümleri değiştirir. |
| 545 | `.closest()` | Kendisi dahil en yakın eşleşeni bulur. |
| 546 | `.matches()` | CSS seçicisiyle eşleşiyor mu? |
| 547 | `.querySelector()` | Alt ağaçta ilk CSS eşleşmesini bulur. |
| 548 | `.querySelectorAll()` | Alt ağaçta CSS eşleşmelerini listeler. |
| 549 | `.getAttribute()` | Özniteliğin metin değerini getirir. |
| 550 | `.getAttributeNames()` | Öznitelik adlarını listeler. |
| 551 | `.getAttributeNS()` | Ad alanıyla öznitelik getirir. |
| 552 | `.hasAttribute()` | Belirtilen öznitelik mevcut mu? |
| 553 | `.hasAttributes()` | Herhangi bir öznitelik var mı? |
| 554 | `.hasAttributeNS()` | Ad alanındaki öznitelik mevcut mu? |
| 555 | `.setAttribute()` | Öznitelik değerini ayarlar. |
| 556 | `.setAttributeNS()` | Ad alanıyla öznitelik ayarlar. |
| 557 | `.removeAttribute()` | Özniteliği kaldırır. |
| 558 | `.removeAttributeNS()` | Ad alanındaki özniteliği kaldırır. |
| 559 | `.toggleAttribute()` | Mantıksal özniteliğin varlığını değiştirir. |
| 560 | `.getBoundingClientRect()` | Görünüm alanına göre sınırları verir. |
| 561 | `.getClientRects()` | Düzen kutularının sınırlarını verir. |
| 562 | `.insertAdjacentElement()` | Belirtilen komşu konuma öğe ekler. |
| 563 | `.insertAdjacentHTML()` | Komşu konuma HTML ayrıştırarak ekler. |
| 564 | `.insertAdjacentText()` | Komşu konuma metin ekler. |
| 565 | `.scroll()` | Kaydırma konumunu ayarlar. |
| 566 | `.scrollBy()` | Belirtilen miktarda kaydırır. |
| 567 | `.scrollTo()` | Belirtilen konuma kaydırır. |
| 568 | `.scrollIntoView()` | Öğeyi görünür alana kaydırır. |
| 569 | `.attachShadow()` | Öğeye gölge DOM kökü bağlar. |
| 570 | `.requestFullscreen()` | Öğeyi tam ekrana geçirmeyi ister. |
| 571 | `.setPointerCapture()` | İşaretçi olaylarını öğeye yakalar. |
| 572 | `.releasePointerCapture()` | İşaretçi yakalamayı bırakır. |
| 573 | `.hasPointerCapture()` | İşaretçi bu öğe tarafından yakalanmış mı? |
| 574 | `.animate()` | Anahtar karelerle animasyon başlatır. |
| 575 | `.getAnimations()` | Öğeye ait animasyonları getirir. |

### HTMLElement

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 576 | `.click()` | Öğede tıklama davranışını tetikler. |
| 577 | `.focus()` | Öğeye klavye odağı verir. |
| 578 | `.blur()` | Öğenin odağını kaldırır. |

### DOMTokenList

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 579 | `.add()` | Sınıf benzeri belirteçler ekler. |
| 580 | `.remove()` | Belirteçleri kaldırır. |
| 581 | `.contains()` | Belirteç mevcut mu? |
| 582 | `.toggle()` | Belirteci ekler veya kaldırır. |
| 583 | `.replace()` | Belirteci başka belirteçle değiştirir. |
| 584 | `.item()` | Konumdaki belirteci alır. |
| 585 | `.entries()` | İndis ve belirteç çiftlerini yineler. |
| 586 | `.forEach()` | Her belirteç için işlev çalıştırır. |
| 587 | `.keys()` | Belirteç indislerini yineler. |
| 588 | `.values()` | Belirteç değerlerini yineler. |

### EventTarget

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 589 | `.addEventListener()` | Olay dinleyicisi ekler. |
| 590 | `.removeEventListener()` | Olay dinleyicisini kaldırır. |
| 591 | `.dispatchEvent()` | Nesne üzerinde olay gönderir. |

### Event

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 592 | `.preventDefault()` | İptal edilebilen varsayılanı engeller. |
| 593 | `.stopPropagation()` | Olayın diğer düğümlere yayılmasını keser. |
| 594 | `.stopImmediatePropagation()` | Sonraki dinleyicileri ve yayılmayı keser. |
| 595 | `.composedPath()` | Olayın geçtiği hedef yolunu verir. |

### HTMLFormElement

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 596 | `.checkValidity()` | Form alanlarının geçerliliğini sınar. |
| 597 | `.reportValidity()` | Geçersiz alanları kullanıcıya bildirir. |
| 598 | `.requestSubmit()` | Doğrulamalı form gönderimi ister. |
| 599 | `.reset()` | Formu başlangıç değerlerine döndürür. |
| 600 | `.submit()` | Doğrulamayı atlayarak formu gönderir. |

<a id="bolum-07"></a>
## Bölüm 07: Tarayıcı: Canvas, çizim ve görseller


### CanvasRenderingContext2D

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 601 | `.save()` | Çizim durumunu yığına kaydeder. |
| 602 | `.restore()` | Kaydedilmiş çizim durumunu geri alır. |
| 603 | `.reset()` | Bağlamı varsayılan durumuna sıfırlar. |
| 604 | `.scale()` | Koordinat sistemini ölçekler. |
| 605 | `.rotate()` | Koordinat sistemini döndürür. |
| 606 | `.translate()` | Koordinat başlangıcını taşır. |
| 607 | `.transform()` | Geçerli dönüşümle matrisi çarpar. |
| 608 | `.setTransform()` | Dönüşüm matrisini değiştirir. |
| 609 | `.resetTransform()` | Dönüşümü birim matrise çevirir. |
| 610 | `.getTransform()` | Geçerli dönüşüm matrisini getirir. |
| 611 | `.createLinearGradient()` | Doğrusal renk geçişi oluşturur. |
| 612 | `.createRadialGradient()` | Radyal renk geçişi oluşturur. |
| 613 | `.createConicGradient()` | Konik renk geçişi oluşturur. |
| 614 | `.createPattern()` | Görselden tekrarlı desen oluşturur. |
| 615 | `.clearRect()` | Dikdörtgen alanı saydamlaştırır. |
| 616 | `.fillRect()` | Dolu dikdörtgen çizer. |
| 617 | `.strokeRect()` | Dikdörtgen kenarlığı çizer. |
| 618 | `.beginPath()` | Yeni çizim yolu başlatır. |
| 619 | `.closePath()` | Geçerli alt yolu kapatır. |
| 620 | `.moveTo()` | Yolun kalem konumunu taşır. |
| 621 | `.lineTo()` | Konuma düz çizgi ekler. |
| 622 | `.bezierCurveTo()` | Kübik Bézier eğrisi ekler. |
| 623 | `.quadraticCurveTo()` | İkinci dereceden Bézier eğrisi ekler. |
| 624 | `.arc()` | Dairesel yay ekler. |
| 625 | `.arcTo()` | Teğetli dairesel yay ekler. |
| 626 | `.ellipse()` | Eliptik yay ekler. |
| 627 | `.rect()` | Dikdörtgen yol ekler. |
| 628 | `.roundRect()` | Yuvarlatılmış dikdörtgen yol ekler. |
| 629 | `.fill()` | Yolun içini doldurur. |
| 630 | `.stroke()` | Yolun kenarını çizer. |
| 631 | `.clip()` | Çizim alanını yolla sınırlar. |
| 632 | `.isPointInPath()` | Nokta yolun içinde mi? |
| 633 | `.isPointInStroke()` | Nokta çizgi alanında mı? |
| 634 | `.fillText()` | Dolu metin çizer. |
| 635 | `.strokeText()` | Metnin dış çizgilerini çizer. |
| 636 | `.measureText()` | Metnin ölçülerini hesaplar. |
| 637 | `.drawImage()` | Görseli veya video karesini çizer. |
| 638 | `.createImageData()` | Boş piksel verisi oluşturur. |
| 639 | `.getImageData()` | Tuvalden piksel verisi okur. |
| 640 | `.putImageData()` | Tuvale doğrudan piksel verisi yazar. |
| 641 | `.setLineDash()` | Kesikli çizgi desenini ayarlar. |
| 642 | `.getLineDash()` | Kesikli çizgi desenini getirir. |

### Canvas · renk ve desen

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 643 | `.CanvasGradient.addColorStop()` | Renk geçişine renk durağı ekler. |
| 644 | `.CanvasPattern.setTransform()` | Desenin dönüşüm matrisini ayarlar. |

### Canvas ve bitmap nesneleri

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 645 | `.HTMLCanvasElement.getContext()` | İstenen çizim bağlamını getirir. |
| 646 | `.HTMLCanvasElement.toDataURL()` | Tuvali veri URL'sine dönüştürür. |
| 647 | `.HTMLCanvasElement.toBlob()` | Tuvali Blob olarak kodlar. |
| 648 | `.HTMLCanvasElement.captureStream()` | Tuvalden canlı medya akışı üretir. |
| 649 | `.HTMLCanvasElement.transferControlToOffscreen()` | Tuval denetimini OffscreenCanvas'a taşır. |
| 650 | `.OffscreenCanvas.getContext()` | Ekran dışı çizim bağlamı alır. |
| 651 | `.OffscreenCanvas.convertToBlob()` | Ekran dışı tuvali Blob'a çevirir. |
| 652 | `.OffscreenCanvas.transferToImageBitmap()` | Son çizimi ImageBitmap olarak aktarır. |
| 653 | `.ImageBitmap.close()` | Görselin kaynaklarını serbest bırakır. |

### Genel işlevler

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 654 | `createImageBitmap()` | Kaynak görselden bitmap oluşturur. |

### Path2D

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 655 | `.addPath()` | Başka yolu mevcut yola ekler. |
| 656 | `.closePath()` | Geçerli alt yolu kapatır. |
| 657 | `.moveTo()` | Yolun kalem konumunu taşır. |
| 658 | `.lineTo()` | Yola düz çizgi ekler. |
| 659 | `.bezierCurveTo()` | Yola kübik eğri ekler. |
| 660 | `.quadraticCurveTo()` | Yola ikinci dereceden eğri ekler. |
| 661 | `.arc()` | Yola dairesel yay ekler. |
| 662 | `.arcTo()` | Yola teğetli yay ekler. |
| 663 | `.ellipse()` | Yola eliptik yay ekler. |
| 664 | `.rect()` | Yola dikdörtgen ekler. |
| 665 | `.roundRect()` | Yola yuvarlatılmış dikdörtgen ekler. |

### DOMMatrix · matris işlemleri

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 666 | `.multiplySelf()` | Matrisi yerinde sağdan çarpar. |
| 667 | `.preMultiplySelf()` | Matrisi yerinde soldan çarpar. |
| 668 | `.translateSelf()` | Matrise yerinde öteleme ekler. |
| 669 | `.scaleSelf()` | Matrise yerinde ölçekleme ekler. |
| 670 | `.scale3dSelf()` | Üç boyutta ortak ölçek uygular. |
| 671 | `.rotateSelf()` | Matrise yerinde dönme ekler. |
| 672 | `.rotateFromVectorSelf()` | Vektör açısına göre yerinde döndürür. |
| 673 | `.rotateAxisAngleSelf()` | Eksen ve açıyla yerinde döndürür. |
| 674 | `.skewXSelf()` | X yönünde yerinde eğme uygular. |
| 675 | `.skewYSelf()` | Y yönünde yerinde eğme uygular. |
| 676 | `.invertSelf()` | Matrisin tersini yerinde alır. |
| 677 | `.setMatrixValue()` | CSS dönüşüm metninden matrisi ayarlar. |
| 678 | `.translate()` | Ötelenmiş yeni matris üretir. |
| 679 | `.scale()` | Ölçeklenmiş yeni matris üretir. |
| 680 | `.scale3d()` | Üç boyutta ölçeklenmiş matris üretir. |
| 681 | `.rotate()` | Döndürülmüş yeni matris üretir. |
| 682 | `.rotateFromVector()` | Vektör açısıyla döndürülmüş matris üretir. |
| 683 | `.rotateAxisAngle()` | Eksen ve açıyla döndürülmüş matris üretir. |
| 684 | `.skewX()` | X yönünde eğilmiş matris üretir. |
| 685 | `.skewY()` | Y yönünde eğilmiş matris üretir. |
| 686 | `.multiply()` | Matris çarpımından yeni matris üretir. |
| 687 | `.flipX()` | X yönünü yansıtan matris üretir. |
| 688 | `.flipY()` | Y yönünü yansıtan matris üretir. |
| 689 | `.inverse()` | Ters matris üretir. |
| 690 | `.transformPoint()` | Noktaya matris dönüşümü uygular. |
| 691 | `.toFloat32Array()` | Matrisi 32 bit kayan diziye çevirir. |
| 692 | `.toFloat64Array()` | Matrisi 64 bit kayan diziye çevirir. |
| 693 | `.toString()` | Matrisi CSS dönüşüm metnine çevirir. |
| 694 | `.toJSON()` | Matris bileşenlerini nesne olarak verir. |

### Nokta ve dikdörtgen nesneleri

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 695 | `.DOMPointReadOnly.matrixTransform()` | Noktayı matrisle dönüştürür. |
| 696 | `.DOMPointReadOnly.toJSON()` | Nokta bileşenlerini nesne olarak verir. |
| 697 | `.DOMRectReadOnly.toJSON()` | Dikdörtgen alanlarını nesne olarak verir. |

### HTMLImageElement

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 698 | `.decode()` | Görselin çözümlenmesini bekler. |

### window

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 699 | `.requestAnimationFrame()` | Sonraki çizim öncesine görev planlar. |
| 700 | `.cancelAnimationFrame()` | Planlanan çizim görevini iptal eder. |

<a id="bolum-08"></a>
## Bölüm 08: Tarayıcı: depolama, performans ve iletişim


### Storage

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 701 | `.getItem()` | Depodan anahtarın değerini okur. |
| 702 | `.setItem()` | Depoya anahtar-değer çifti yazar. |
| 703 | `.removeItem()` | Anahtarı depodan kaldırır. |
| 704 | `.clear()` | Depoyu tamamen boşaltır. |
| 705 | `.key()` | Konumdaki anahtarı getirir. |

### CacheStorage

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 706 | `.open()` | Adlandırılmış önbelleği açar veya oluşturur. |
| 707 | `.has()` | Adlandırılmış önbellek var mı? |
| 708 | `.delete()` | Adlandırılmış önbelleği kaldırır. |
| 709 | `.keys()` | Önbellek adlarını listeler. |
| 710 | `.match()` | Önbelleklerde isteğe uygun yanıt arar. |

### Cache

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 711 | `.add()` | İstek sonucunu indirip önbelleğe ekler. |
| 712 | `.addAll()` | İstek sonuçlarını topluca önbelleğe ekler. |
| 713 | `.put()` | İstek ve yanıtı önbelleğe yazar. |
| 714 | `.match()` | Önbellekte ilk uygun yanıtı bulur. |
| 715 | `.matchAll()` | Önbellekte uygun bütün yanıtları bulur. |
| 716 | `.delete()` | Eşleşen önbellek kaydını siler. |
| 717 | `.keys()` | Önbellekteki istekleri listeler. |

### IndexedDB · veritabanı nesneleri

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 718 | `.Factory.open()` | IndexedDB veritabanını açar. |
| 719 | `.Factory.deleteDatabase()` | IndexedDB veritabanını siler. |
| 720 | `.Factory.cmp()` | İki IndexedDB anahtarını karşılaştırır. |
| 721 | `.Database.createObjectStore()` | Sürüm yükseltmede nesne deposu oluşturur. |
| 722 | `.Database.deleteObjectStore()` | Sürüm yükseltmede nesne deposunu siler. |
| 723 | `.Database.transaction()` | Veritabanı işlemi başlatır. |
| 724 | `.Database.close()` | Veritabanı bağlantısını kapatır. |
| 725 | `.Transaction.objectStore()` | İşlemdeki nesne deposunu getirir. |
| 726 | `.Transaction.abort()` | Veritabanı işlemini geri alır. |
| 727 | `.Transaction.commit()` | İşlemin tamamlanmasını başlatır. |
| 728 | `.ObjectStore.add()` | Yeni kayıt ekler; mevcut anahtarda hata verir. |
| 729 | `.ObjectStore.put()` | Kayıt ekler veya günceller. |
| 730 | `.ObjectStore.get()` | Anahtarla ilk kaydı getirir. |
| 731 | `.ObjectStore.getAll()` | Eşleşen kayıtları getirir. |
| 732 | `.ObjectStore.getKey()` | Eşleşen ilk anahtarı getirir. |
| 733 | `.ObjectStore.getAllKeys()` | Eşleşen anahtarları getirir. |
| 734 | `.ObjectStore.delete()` | Anahtar veya aralıktaki kayıtları siler. |
| 735 | `.ObjectStore.clear()` | Depodaki bütün kayıtları siler. |
| 736 | `.ObjectStore.count()` | Eşleşen kayıt sayısını verir. |
| 737 | `.ObjectStore.createIndex()` | Sürüm yükseltmede indeks oluşturur. |
| 738 | `.ObjectStore.deleteIndex()` | Sürüm yükseltmede indeksi siler. |
| 739 | `.ObjectStore.index()` | Adlandırılmış indeksi getirir. |
| 740 | `.ObjectStore.openCursor()` | Kayıt gezgini açar. |
| 741 | `.ObjectStore.openKeyCursor()` | Anahtar gezgini açar. |
| 742 | `.Index.get()` | İndeksten ilk kayıt değerini getirir. |
| 743 | `.Index.getAll()` | İndeksten eşleşen değerleri getirir. |
| 744 | `.Index.getKey()` | İndeksten ilk asıl anahtarı getirir. |
| 745 | `.Index.getAllKeys()` | İndeksten asıl anahtarları getirir. |
| 746 | `.Index.count()` | İndeksteki eşleşmeleri sayar. |
| 747 | `.Index.openCursor()` | İndeks üzerinde kayıt gezgini açar. |
| 748 | `.Index.openKeyCursor()` | İndeks üzerinde anahtar gezgini açar. |
| 749 | `.Cursor.advance()` | Gezgini belirtilen kayıt sayısı ilerletir. |
| 750 | `.Cursor.continue()` | Gezgini sonraki uygun kayda ilerletir. |
| 751 | `.Cursor.continuePrimaryKey()` | İndeks ve asıl anahtara göre ilerler. |
| 752 | `.Cursor.delete()` | Gezginin geçerli kaydını siler. |
| 753 | `.Cursor.update()` | Gezginin geçerli kaydını günceller. |
| 754 | `.KeyRange.only() [statik]` | Tek anahtarı içeren aralık oluşturur. |
| 755 | `.KeyRange.bound() [statik]` | Alt ve üst sınırlı aralık oluşturur. |
| 756 | `.KeyRange.lowerBound() [statik]` | Alt sınırlı anahtar aralığı oluşturur. |
| 757 | `.KeyRange.upperBound() [statik]` | Üst sınırlı anahtar aralığı oluşturur. |
| 758 | `.KeyRange.includes()` | Anahtarın aralıkta olduğunu sınar. |

### Performans ölçümü ve gözlem

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 759 | `.Performance.now()` | Yüksek çözünürlüklü zaman sayacı verir. |
| 760 | `.Performance.mark()` | Adlandırılmış zaman işareti ekler. |
| 761 | `.Performance.measure()` | İşaretler arası süre kaydı üretir. |
| 762 | `.Performance.clearMarks()` | Zaman işaretlerini temizler. |
| 763 | `.Performance.clearMeasures()` | Süre kayıtlarını temizler. |
| 764 | `.Performance.getEntries()` | Performans kayıtlarını getirir. |
| 765 | `.Performance.getEntriesByName()` | Ada göre performans kayıtları getirir. |
| 766 | `.Performance.getEntriesByType()` | Türe göre performans kayıtları getirir. |
| 767 | `.Performance.clearResourceTimings()` | Kaynak zamanlama kayıtlarını temizler. |
| 768 | `.Performance.setResourceTimingBufferSize()` | Kaynak kayıt tamponunun boyutunu ayarlar. |
| 769 | `.Performance.toJSON()` | Performans nesnesini sade nesne yapar. |
| 770 | `.PerformanceObserver.observe()` | Seçilen performans kayıtlarını izler. |
| 771 | `.PerformanceObserver.disconnect()` | Performans izlemeyi durdurur. |
| 772 | `.PerformanceObserver.takeRecords()` | Bekleyen performans kayıtlarını alır. |
| 773 | `.EntryList.getEntries()` | Gözlenen kayıtların hepsini alır. |
| 774 | `.EntryList.getEntriesByName()` | Gözlenen kayıtları ada göre seçer. |
| 775 | `.EntryList.getEntriesByType()` | Gözlenen kayıtları türe göre seçer. |

### DOM gözlemcileri

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 776 | `.MutationObserver.observe()` | DOM değişikliklerini izler. |
| 777 | `.MutationObserver.disconnect()` | DOM izlemeyi durdurur. |
| 778 | `.MutationObserver.takeRecords()` | Bekleyen DOM değişimlerini alır. |
| 779 | `.ResizeObserver.observe()` | Öğenin boyut değişimini izler. |
| 780 | `.ResizeObserver.unobserve()` | Öğenin boyut izlemesini durdurur. |
| 781 | `.ResizeObserver.disconnect()` | Bütün boyut izlemelerini durdurur. |
| 782 | `.IntersectionObserver.observe()` | Öğenin görünürlük kesişimini izler. |
| 783 | `.IntersectionObserver.unobserve()` | Öğenin kesişim izlemesini durdurur. |
| 784 | `.IntersectionObserver.disconnect()` | Bütün kesişim izlemelerini durdurur. |
| 785 | `.IntersectionObserver.takeRecords()` | Bekleyen kesişim kayıtlarını alır. |

### Worker ve mesajlaşma nesneleri

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 786 | `.Worker.postMessage()` | Worker'a mesaj gönderir. |
| 787 | `.Worker.terminate()` | Worker yürütmesini sonlandırır. |
| 788 | `.MessagePort.postMessage()` | Port üzerinden mesaj gönderir. |
| 789 | `.MessagePort.start()` | Porta mesaj teslimini başlatır. |
| 790 | `.MessagePort.close()` | Mesaj portunu kapatır. |
| 791 | `.BroadcastChannel.postMessage()` | Aynı adlı kanala mesaj yayınlar. |
| 792 | `.BroadcastChannel.close()` | Yayın kanalını kapatır. |
| 793 | `.WebSocket.send()` | Açık bağlantıda veri gönderir. |
| 794 | `.WebSocket.close()` | WebSocket bağlantısını kapatır. |
| 795 | `.EventSource.close()` | Sunucu olay akışını kapatır. |

### History

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 796 | `.back()` | Geçmişte bir kayıt geri gider. |
| 797 | `.forward()` | Geçmişte bir kayıt ileri gider. |
| 798 | `.go()` | Geçmişte belirtilen miktarda ilerler. |
| 799 | `.pushState()` | Geçmişe sayfa yüklemeden kayıt ekler. |
| 800 | `.replaceState()` | Geçerli geçmiş kaydını değiştirir. |

<a id="bolum-09"></a>
## Bölüm 09: Node.js: dosyalar, yollar ve işletim sistemi


### fs

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 801 | `.access()` | Dosya erişimini geri çağırımla denetler. |
| 802 | `.appendFile()` | Dosyanın sonuna veri ekler. |
| 803 | `.chmod()` | Dosya izinlerini değiştirir. |
| 804 | `.chown()` | Dosyanın sahip ve grubunu değiştirir. |
| 805 | `.close()` | Dosya tanımlayıcısını kapatır. |
| 806 | `.copyFile()` | Dosyayı başka yola kopyalar. |
| 807 | `.cp()` | Dosya veya klasör ağacını kopyalar. |
| 808 | `.createReadStream()` | Dosyadan okunabilir akış açar. |
| 809 | `.createWriteStream()` | Dosyaya yazılabilir akış açar. |
| 810 | `.existsSync()` | Yolun varlığını eşzamanlı denetler. |
| 811 | `.fchmod()` | Açık dosyanın izinlerini değiştirir. |
| 812 | `.fchown()` | Açık dosyanın sahipliğini değiştirir. |
| 813 | `.fdatasync()` | Dosya veri değişikliklerini diske aktarır. |
| 814 | `.fstat()` | Açık dosyanın metaverisini getirir. |
| 815 | `.fsync()` | Dosya değişikliklerini diske eşler. |
| 816 | `.ftruncate()` | Açık dosyanın uzunluğunu değiştirir. |
| 817 | `.futimes()` | Açık dosyanın zamanlarını değiştirir. |
| 818 | `.link()` | Sabit dosya bağlantısı oluşturur. |
| 819 | `.lstat()` | Bağlantıyı izlemeden metaveri okur. |
| 820 | `.mkdir()` | Klasör oluşturur. |
| 821 | `.mkdtemp()` | Benzersiz geçici klasör oluşturur. |
| 822 | `.open()` | Dosyayı açıp tanımlayıcı verir. |
| 823 | `.opendir()` | Klasör okuma nesnesi açar. |
| 824 | `.read()` | Açık dosyadan tampona veri okur. |
| 825 | `.readdir()` | Klasör öğelerini okur. |
| 826 | `.readFile()` | Dosyanın bütün içeriğini okur. |
| 827 | `.readlink()` | Sembolik bağlantının hedefini okur. |
| 828 | `.realpath()` | Bağlantıları çözümlenmiş yol verir. |
| 829 | `.rename()` | Dosya veya klasörü yeniden adlandırır. |
| 830 | `.rm()` | Dosya veya klasörü kaldırır. |
| 831 | `.rmdir()` | Boş klasörü kaldırır. |
| 832 | `.stat()` | Dosya metaverisini getirir. |
| 833 | `.statfs()` | Dosya sistemi istatistiklerini getirir. |
| 834 | `.symlink()` | Sembolik bağlantı oluşturur. |
| 835 | `.truncate()` | Dosyanın uzunluğunu değiştirir. |
| 836 | `.unlink()` | Dosya adını dosya sisteminden kaldırır. |
| 837 | `.unwatchFile()` | Dosya değişikliği yoklamasını durdurur. |
| 838 | `.utimes()` | Dosya erişim ve değişim zamanını ayarlar. |
| 839 | `.watch()` | Dosya veya klasör değişikliklerini izler. |
| 840 | `.watchFile()` | Dosya değişikliklerini yoklayarak izler. |
| 841 | `.write()` | Açık dosyaya veri yazar. |
| 842 | `.writeFile()` | Dosyaya bütün içeriği yazar. |
| 843 | `.writev()` | Birden fazla tamponu dosyaya yazar. |
| 844 | `.readv()` | Dosyadan birden fazla tampona okur. |
| 845 | `.accessSync()` | Dosya erişimini eşzamanlı denetler. |
| 846 | `.appendFileSync()` | Dosyaya eşzamanlı veri ekler. |
| 847 | `.copyFileSync()` | Dosyayı eşzamanlı kopyalar. |
| 848 | `.mkdirSync()` | Klasörü eşzamanlı oluşturur. |
| 849 | `.readFileSync()` | Dosyayı eşzamanlı okur. |
| 850 | `.writeFileSync()` | Dosyayı eşzamanlı yazar. |
| 851 | `.readdirSync()` | Klasör öğelerini eşzamanlı okur. |
| 852 | `.renameSync()` | Yolu eşzamanlı yeniden adlandırır. |
| 853 | `.rmSync()` | Dosya veya klasörü eşzamanlı kaldırır. |
| 854 | `.statSync()` | Metaveriyi eşzamanlı getirir. |

### fs.promises

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 855 | `.access()` | Promise ile erişim denetler. |
| 856 | `.appendFile()` | Promise ile dosyaya veri ekler. |
| 857 | `.copyFile()` | Promise ile dosya kopyalar. |
| 858 | `.cp()` | Promise ile klasör ağacı kopyalar. |
| 859 | `.mkdir()` | Promise ile klasör oluşturur. |
| 860 | `.mkdtemp()` | Promise ile geçici klasör oluşturur. |
| 861 | `.open()` | Promise ile FileHandle açar. |
| 862 | `.opendir()` | Promise ile klasör nesnesi açar. |
| 863 | `.readdir()` | Promise ile klasör öğelerini okur. |
| 864 | `.readFile()` | Promise ile dosya içeriğini okur. |
| 865 | `.readlink()` | Promise ile bağlantı hedefi okur. |
| 866 | `.realpath()` | Promise ile gerçek yolu çözümler. |
| 867 | `.rename()` | Promise ile yolu yeniden adlandırır. |
| 868 | `.rm()` | Promise ile dosya veya klasör kaldırır. |
| 869 | `.stat()` | Promise ile dosya metaverisi getirir. |
| 870 | `.unlink()` | Promise ile dosya bağlantısını siler. |
| 871 | `.writeFile()` | Promise ile dosya içeriğini yazar. |

### path

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 872 | `.basename()` | Yolun son bileşenini getirir. |
| 873 | `.dirname()` | Yolun klasör bölümünü getirir. |
| 874 | `.extname()` | Dosya uzantısını getirir. |
| 875 | `.format()` | Yol nesnesinden metin oluşturur. |
| 876 | `.isAbsolute()` | Yol mutlak mı? |
| 877 | `.join()` | Yol bileşenlerini birleştirir. |
| 878 | `.normalize()` | Ayırıcı ve nokta bileşenlerini düzeltir. |
| 879 | `.parse()` | Yolu bileşen nesnesine ayırır. |
| 880 | `.relative()` | İki yol arasındaki göreli yolu verir. |
| 881 | `.resolve()` | Bileşenlerden mutlak yol çözümler. |
| 882 | `.toNamespacedPath()` | Windows ad alanı yoluna dönüştürür. |

### os

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 883 | `.arch()` | Çalışma zamanının işlemci mimarisini verir. |
| 884 | `.availableParallelism()` | Önerilen paralellik düzeyini verir. |
| 885 | `.cpus()` | Mantıksal işlemci bilgilerini getirir. |
| 886 | `.endianness()` | İşlemcinin bayt sırasını verir. |
| 887 | `.freemem()` | Boş sistem belleğini bayt verir. |
| 888 | `.homedir()` | Kullanıcının ev klasörünü getirir. |
| 889 | `.hostname()` | Makine adını getirir. |
| 890 | `.loadavg()` | Sistem yük ortalamalarını verir. |
| 891 | `.networkInterfaces()` | Ağ arayüzü adreslerini listeler. |
| 892 | `.platform()` | İşletim sistemi platformunu verir. |
| 893 | `.release()` | İşletim sistemi sürümünü verir. |
| 894 | `.tmpdir()` | Geçici dosya klasörünü verir. |
| 895 | `.totalmem()` | Toplam sistem belleğini bayt verir. |
| 896 | `.type()` | İşletim sistemi türünü verir. |
| 897 | `.uptime()` | Sistemin açık kalma süresini verir. |
| 898 | `.userInfo()` | Geçerli kullanıcı bilgisini verir. |
| 899 | `.version()` | İşletim sistemi sürüm metnini verir. |
| 900 | `.machine()` | Makinenin donanım türünü verir. |

<a id="bolum-10"></a>
## Bölüm 10: Node.js: Buffer, kriptografi ve olaylar


### Buffer

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 901 | `.alloc() [statik]` | Başlatılmış bayt tamponu oluşturur. |
| 902 | `.allocUnsafe() [statik]` | İçeriği başlatılmamış tampon ayırır. |
| 903 | `.allocUnsafeSlow() [statik]` | Havuz dışı başlatılmamış tampon ayırır. |
| 904 | `.byteLength() [statik]` | Metnin kodlanmış bayt uzunluğunu verir. |
| 905 | `.compare() [statik]` | İki tamponun bayt sırasını karşılaştırır. |
| 906 | `.concat() [statik]` | Tamponları yeni tampona birleştirir. |
| 907 | `.from() [statik]` | Metin, dizi veya bellekten tampon kurar. |
| 908 | `.isBuffer() [statik]` | Değer Buffer nesnesi mi? |
| 909 | `.isEncoding() [statik]` | Kodlama adı destekleniyor mu? |
| 910 | `.compare()` | Tampon bölümlerini karşılaştırır. |
| 911 | `.copy()` | Baytları başka tampona kopyalar. |
| 912 | `.equals()` | Tampon içerikleri eşit mi? |
| 913 | `.fill()` | Tamponu verilen değerle doldurur. |
| 914 | `.includes()` | Bayt veya alt dizi mevcut mu? |
| 915 | `.indexOf()` | İlk eşleşen bayt konumunu bulur. |
| 916 | `.lastIndexOf()` | Son eşleşen bayt konumunu bulur. |
| 917 | `.readBigInt64BE()` | Büyük uçlu işaretli 64 bit tamsayı okur. |
| 918 | `.readBigInt64LE()` | Küçük uçlu işaretli 64 bit tamsayı okur. |
| 919 | `.readBigUInt64BE()` | Büyük uçlu işaretsiz 64 bit tamsayı okur. |
| 920 | `.readBigUInt64LE()` | Küçük uçlu işaretsiz 64 bit tamsayı okur. |
| 921 | `.readDoubleBE()` | Büyük uçlu 64 bit kayan sayı okur. |
| 922 | `.readDoubleLE()` | Küçük uçlu 64 bit kayan sayı okur. |
| 923 | `.readFloatBE()` | Büyük uçlu 32 bit kayan sayı okur. |
| 924 | `.readFloatLE()` | Küçük uçlu 32 bit kayan sayı okur. |
| 925 | `.readInt8()` | İşaretli sekiz bit tamsayı okur. |
| 926 | `.readInt16BE()` | Büyük uçlu işaretli 16 bit sayı okur. |
| 927 | `.readInt16LE()` | Küçük uçlu işaretli 16 bit sayı okur. |
| 928 | `.readInt32BE()` | Büyük uçlu işaretli 32 bit sayı okur. |
| 929 | `.readInt32LE()` | Küçük uçlu işaretli 32 bit sayı okur. |
| 930 | `.readIntBE()` | Büyük uçlu değişken baytlı tamsayı okur. |
| 931 | `.readIntLE()` | Küçük uçlu değişken baytlı tamsayı okur. |
| 932 | `.readUInt8()` | İşaretsiz sekiz bit tamsayı okur. |
| 933 | `.readUInt16BE()` | Büyük uçlu işaretsiz 16 bit sayı okur. |
| 934 | `.readUInt16LE()` | Küçük uçlu işaretsiz 16 bit sayı okur. |
| 935 | `.readUInt32BE()` | Büyük uçlu işaretsiz 32 bit sayı okur. |
| 936 | `.readUInt32LE()` | Küçük uçlu işaretsiz 32 bit sayı okur. |
| 937 | `.readUIntBE()` | Büyük uçlu işaretsiz tamsayı okur. |
| 938 | `.readUIntLE()` | Küçük uçlu işaretsiz tamsayı okur. |
| 939 | `.subarray()` | Ortak bellekte alt tampon görünümü verir. |
| 940 | `.swap16()` | Her 16 bitlik grubun bayt sırasını değiştirir. |
| 941 | `.swap32()` | Her 32 bitlik grubun bayt sırasını değiştirir. |
| 942 | `.swap64()` | Her 64 bitlik grubun bayt sırasını değiştirir. |
| 943 | `.toJSON()` | Tamponu JSON uyumlu nesne yapar. |
| 944 | `.toString()` | Baytları belirtilen kodlamayla çözer. |
| 945 | `.write()` | Metni tampona kodlayarak yazar. |
| 946 | `.writeBigInt64BE()` | Büyük uçlu işaretli 64 bit tamsayı yazar. |
| 947 | `.writeBigInt64LE()` | Küçük uçlu işaretli 64 bit tamsayı yazar. |
| 948 | `.writeBigUInt64BE()` | Büyük uçlu işaretsiz 64 bit tamsayı yazar. |
| 949 | `.writeBigUInt64LE()` | Küçük uçlu işaretsiz 64 bit tamsayı yazar. |
| 950 | `.writeDoubleBE()` | Büyük uçlu 64 bit kayan sayı yazar. |
| 951 | `.writeDoubleLE()` | Küçük uçlu 64 bit kayan sayı yazar. |
| 952 | `.writeFloatBE()` | Büyük uçlu 32 bit kayan sayı yazar. |
| 953 | `.writeFloatLE()` | Küçük uçlu 32 bit kayan sayı yazar. |
| 954 | `.writeInt8()` | İşaretli sekiz bit tamsayı yazar. |
| 955 | `.writeInt16BE()` | Büyük uçlu işaretli 16 bit sayı yazar. |
| 956 | `.writeInt16LE()` | Küçük uçlu işaretli 16 bit sayı yazar. |
| 957 | `.writeInt32BE()` | Büyük uçlu işaretli 32 bit sayı yazar. |
| 958 | `.writeInt32LE()` | Küçük uçlu işaretli 32 bit sayı yazar. |
| 959 | `.writeUInt8()` | İşaretsiz sekiz bit tamsayı yazar. |
| 960 | `.writeUInt16BE()` | Büyük uçlu işaretsiz 16 bit sayı yazar. |
| 961 | `.writeUInt16LE()` | Küçük uçlu işaretsiz 16 bit sayı yazar. |
| 962 | `.writeUInt32BE()` | Büyük uçlu işaretsiz 32 bit sayı yazar. |
| 963 | `.writeUInt32LE()` | Küçük uçlu işaretsiz 32 bit sayı yazar. |

### crypto

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 964 | `.createHash()` | Özet hesaplama nesnesi oluşturur. |
| 965 | `.createHmac()` | Anahtarlı özet nesnesi oluşturur. |
| 966 | `.createCipheriv()` | Anahtar ve IV ile şifreleyici oluşturur. |
| 967 | `.createDecipheriv()` | Anahtar ve IV ile çözücü oluşturur. |
| 968 | `.createSign()` | Dijital imza nesnesi oluşturur. |
| 969 | `.createVerify()` | Dijital imza doğrulayıcısı oluşturur. |
| 970 | `.randomBytes()` | Kriptografik rastgele baytlar üretir. |
| 971 | `.randomFill()` | Tamponu rastgele baytlarla doldurur. |
| 972 | `.randomInt()` | Kriptografik rastgele tamsayı üretir. |
| 973 | `.randomUUID()` | Rastgele UUID üretir. |
| 974 | `.pbkdf2()` | PBKDF2 ile anahtar türetir. |
| 975 | `.scrypt()` | scrypt ile anahtar türetir. |
| 976 | `.hkdf()` | HKDF ile anahtar türetir. |
| 977 | `.timingSafeEqual()` | Eş uzunluktaki baytları sabit zamanla sınar. |
| 978 | `.generateKeyPair()` | Açık ve özel anahtar çifti üretir. |
| 979 | `.createPublicKey()` | Açık anahtar nesnesi oluşturur. |
| 980 | `.createPrivateKey()` | Özel anahtar nesnesi oluşturur. |
| 981 | `.createSecretKey()` | Simetrik anahtar nesnesi oluşturur. |
| 982 | `.sign()` | Veri için dijital imza üretir. |
| 983 | `.verify()` | Verinin dijital imzasını doğrular. |
| 984 | `.publicEncrypt()` | Açık anahtarla şifreler. |
| 985 | `.privateDecrypt()` | Özel anahtarla şifreyi çözer. |
| 986 | `.getHashes()` | Desteklenen özet algoritmalarını listeler. |
| 987 | `.getCiphers()` | Desteklenen şifre algoritmalarını listeler. |

### EventEmitter

| No | Metot / kalıp | Türkçe açıklama |
| --- | --- | --- |
| 988 | `.on()` | Olay dinleyicisi ekler. |
| 989 | `.once()` | Bir kez çalışan dinleyici ekler. |
| 990 | `.off()` | Olay dinleyicisini kaldırır. |
| 991 | `.emit()` | Adlandırılmış olayı tetikler. |
| 992 | `.addListener()` | Dinleyici ekler; on ile eşdeğerdir. |
| 993 | `.removeListener()` | Belirtilen dinleyiciyi kaldırır. |
| 994 | `.removeAllListeners()` | Olayın veya tüm olayların dinleyicisini siler. |
| 995 | `.listeners()` | Olay dinleyicilerini listeler. |
| 996 | `.rawListeners()` | Sarmalayıcılar dahil dinleyicileri verir. |
| 997 | `.listenerCount()` | Olay dinleyicilerini sayar. |
| 998 | `.eventNames()` | Dinleyicisi bulunan olay adlarını listeler. |
| 999 | `.setMaxListeners()` | Dinleyici uyarı eşiğini ayarlar. |
| 1000 | `.getMaxListeners()` | Dinleyici uyarı eşiğini getirir. |
