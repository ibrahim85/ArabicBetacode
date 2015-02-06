# Arabic betaCode

 Although both Windows and Mac OS now support Arabic, it is still quite difficult to type and edit Arabic texts. In particular, it is extremely difficult to edit and manipulate fully vocalized texts, since most fonts either render “short vowels” (*ḥarakāt*) invisible, or do not render them properly. Moreover, because of the “stacking,” i.e. when “short vowels” are placed on top of each other, it becomes impossible to edit texts, one is forced to delete and re-type, rather then to edit (and still, because of visual issues, there is no guarantee that all the letters and “short vowels” are actually in the right order). **betaCode** can help to make typing fully-vocalized Arabic texts possible and easy on any machine and render it into various transliteration conventions and into Arabic script (scroll below for examples). 

**betaCode** is first converted into a one-to-one transliteration scheme (the one to rule them all), which combines one-to-one transliteration conventions from major academic transliteration schemes. Such scheme is necessary, since none of the existing academic transliteration schemes (American/Library of Congress, British, French, German) allow to represent Arabic text unambiguously for computational purposes. Arabic **betaCode** transliteration can be then converted into any transliteration conventions. At the moment the following schemes are implemented (not yet fully):

* Library of Congress Romanization of Arabic
* Simplified transliteration (essentially, LOC but with diacritics removed)
* Arabic script (*hamzaŧ* orthography are implemented, but may require some additional testing)

**NB:** The idea of **betaCode** is borrowed from the Classicists who developed ["a method of representing, using only ASCII characters, characters and formatting found in ancient Greek texts"](http://en.wikipedia.org/wiki/Beta_Code). The current **betaCode** is inspired by, and is therefore quite similar to, the [arabTex scheme](http://www2.informatik.uni-stuttgart.de/ivi/bs/research/arab_e.htm). Linguists working with Arabic are commonly using (Buckwalter transliteration)[http://en.wikipedia.org/wiki/Buckwalter_transliteration], which essentially is a betaCode, but less readable. 

## Basic principles of *betaCode*:
Every Arabic letter is betaCoded with its one-letter equivalent (thus pulling from different academic transliteration schemes),
preceded (if necessary) with a technical symbol that is similar to a diacritical mark in the transliterated version. Thus, most common symbols are as follows:

* **\_** (underscore), if letter can be transliterated with *macron*/*breve* below or above (ā, ṯ, ḫ, ḏ, ū, ī)
* **.** (period), or  <b>\*</b> (asterisk), if letter can be transliterated transliterated with *dot* below or above (ḥ, ṣ, ḍ, ṭ, ẓ, ġ, ḳ)
* **^** (caret), if letter can be transliterated with *caron* (ǧ, š)
* plus some new combinations (scroll down for the complete table)

## Running the converter
* clone the repository
* save texts that must be transliterated (i.e., the text is in English, but has some Arabic terms that must be transliterated) into “./to\_translit” (follow the format of given in the example file).
* save texts that must be fully transliterated or/and converted into Arabic script (i.e., the entire texts is in Arabic) into “./to_arabic/” (follow the format given in the example file).
* run the script “\_generateBetaCode.py”.
* converted texts (in all available modes of conversion) will be automatically added after the betaCoded texts.
* if you need to make any changes, edit your initial betaCoded text and run the script again, converted results will be replaced with updated versions.

## betaCode and One-To-One Transliteration

| betacode | translit | Arabic letter |
|----------|-----------------|---------------|
| **\_a** | ā | *alif* |
| **b** | b | *bā’* |
| **t** | t | *tā’* |
| **\_t** | ṯ | *thā’* |
| **^g, j** | ǧ | *jīm* |
| **\*h, .h** | ḥ | *ḥā’* |
| **\_h** | ḫ | *khā’* |
| **d** | d | *dāl* |
| **\_d** | ḏ | *dhāl* |
| **r** | r | *rā’* |
| **z** | z | *zayn* |
| **s** | s | *sīn* |
| **^s** | š | *shīn* |
| **\*s, .s** | ṣ | *ṣād* |
| **\*d, .d** | ḍ | *ḍād* |
| **\*t, .t** | ṭ | *ṭā’* |
| **\*z, .z** | ẓ | *ẓā’* |
| **`** | ʿ | *‘ayn* |
| **\*g, .g** | ġ | *ghayn* |
| **f** | f | *fā’* |
| **\*k, .k, q** | ḳ | *qāf* |
| **k** | k | *kāf* |
| **l** | l | *lām* |
| **m** | m | *mīm* |
| **n** | n | *nūn* |
| **h** | h | *hā’* |
| **w** | w | *wāw* |
| **\_u** | ū | *wāw* |
| **y** | y | *yā’* |
| **\_i** | ī | *yā’* |

## Non-alphabetic letters
| **betacode** | translit | Arabic |
|----------|-----------------|---------------|
| **'** | ʾ | *hamzaŧ* |
| **/a** | á | *alif maqṣūraŧ* |
| **:t** | ŧ | *tā’ marbūṭaŧ* |

## Vowels

| **betacode** | translit | Arabic |
|----------|-----------------|---------------|
| **~a** | ã | *dagger alif* |
| **a** | a | *fatḥaŧ* |
| **u** | u | *ḍammaŧ* |
| **i** | i | *kasraŧ* |
| **.n** | ȵ | *n of tanwīn* |
| **.a** | å | *silent alif* |
| **.w** | ů | *silent wāw* |

## Additional *betaCode* rules

* attached prepositions/conjunctions must be separated with "-", i.e.:
	* ``` bi-Llahi  ```
	* ``` fa-_dahaba ```
* *tāʾ marbūṭaŧ*: add "+" after *tāʾ marbūṭaŧ*, if the first word of *iḏāfaŧ*
	* ``` `_amma:t+u Ba.gd_ada ```, but:
	* ``` al-`_amma:tu f_i Ba.gd_ada ```
* more to be added...


# Examples 

### betaCode Example

NB: These are examples of converting betaCode to full transliteration and Arabic script. The very last paragraph showcases conversion of hamza in different positions.

q\_ala 'ab\_u Mas\`\_udi.n :: 'an\_a qad sami\`tu h~a\_d\_a min ras\_uli All~ahi ( .sl\`m )

.hadda\_ta-n\_a \`Amru.w bnu R\_afi\`i.n , .hadda\_ta-n\_a \`Abdu All~ahi bnu al-Mub\_araki , \`an Mu.hammadi bni 'is.h\_aqa , \`an Mu.hammadi bni ^Ga\`fari.n , \`an \`Ubaydi All~ahi bni \`Abdi All~ahi bni \`Umara , \`an 'Ab\_i-hi , \`ani al-nabiyyi ( .sl\`m ) na.hwa-hu

'a\_hbara-n\_a Qutayba:tu q\_ala , .hadda\_ta-n\_a Sufy\_anu , \`an Ya.hy/a bni Sa\`\_idi.n , \`an 'Ab\_i Bakri bni Mu.hammadi.n , \`an \`Umara bni \`Abdi al-\`Az\_izi , \`an 'Ab\_i Bakri bni \`Abdi al-Ra.hm~ani bni al-.H\_ari\_ti bni Hi^s\_ami.n , \`an 'Ab\_i Hurayra:ta mi\_tla-hu

Ta.hw\_ilu al-.hamza:ti ( kalim\_atu.n mufrada:tu.n )

'amru.n 'unsu.n 'insu.n '\_im\_anu.n
'\_aya:tu.n '\_amana mas'ala:tu.n sa'ala ra'su.n qur'\_anu.n ta'\_amara
\_di'bu.n as'ila:tu.n q\_ari'i-hi su'lu.n mas'\_ulu.n
tak\_afu'u-hu su'ila q\_ari'i-hi \_di'\_abu.n ra'\_isu.n
bu'isa ru'\_ufu.n ra'\_ufu.n su'\_alu.n mu'arri\_hu.n
abn\_a'a-hu abn\_a'u-hu abn\_a'i-hi ^say'a.n \_ha.t\_i'a:tu.n
.daw'u-hu .d\_u'u-hu .daw'a-hu .daw'i-hi mur\_u'a:tu.n
'abn\_a'i-hi bar\_i'u-hu s\_u'ila f\_ilu.n f\_annu.n f\_unnu.n
s\_a'ala fu'\_adu.n ^surak\_a'u-hu ri'\_asa:tu.n tahni'a:tu.n
daf\_a'a:tu.n .taff\_a'a:tu.n ta'r\_i\_hu.n fa'ru.n
^say'u.n ^say'i.n ^say'a.n  .daw'u.n .daw'i.n .daw'a.n
juz'u.n  juz'i.n  juz'a.n mabda'u.n mabda'i.n mabda'a.n
naba'a q\_ari'u.n tak\_afu'u.n tak\_afu'i.n tak\_afu'a.n
abn\_a'u abn\_a'i abn\_a'a jar\_i'u.n maqr\_u'u.n .daw'u.n ^say'u.n juz'u.n
\`ulam\_a'u al-\`ulam\_a'i al-\`ulam\_a'a \`Amru.n.w wa-fa\`al\_u.a


## betaCode converted into one-to-one translit

ḳāla ʾabū Masʿūdiȵ :: ʾanā ḳad samiʿtu hãḏā min rasūli Allãhi ( ṣlʿm )

ḥaddaṯa-nā ʿAmruů bnu Rāfiʿiȵ , ḥaddaṯa-nā ʿAbdu Allãhi bnu al-Mubāraki , ʿan Muḥammadi bni ʾisḥāḳa , ʿan Muḥammadi bni Ǧaʿfariȵ , ʿan ʿUbaydi Allãhi bni ʿAbdi Allãhi bni ʿUmara , ʿan ʾAbī-hi , ʿani al-nabiyyi ( ṣlʿm ) naḥwa-hu

ʾaḫbara-nā Ḳutaybaŧu ḳāla , ḥaddaṯa-nā Sufyānu , ʿan Yaḥyá bni Saʿīdiȵ , ʿan ʾAbī Bakri bni Muḥammadiȵ , ʿan ʿUmara bni ʿAbdi al-ʿAzīzi , ʿan ʾAbī Bakri bni ʿAbdi al-Raḥmãni bni al-Ḥāriṯi bni Hišāmiȵ , ʿan ʾAbī Hurayraŧa miṯla-hu

Taḥwīlu al-ḥamzaŧi ( kalimātuȵ mufradaŧuȵ )

ʾamruȵ ʾunsuȵ ʾinsuȵ ʾīmānuȵ
ʾāyaŧuȵ ʾāmana masʾalaŧuȵ saʾala raʾsuȵ ḳurʾānuȵ taʾāmara
ḏiʾbuȵ asʾilaŧuȵ ḳāriʾi-hi suʾluȵ masʾūluȵ
takāfuʾu-hu suʾila ḳāriʾi-hi ḏiʾābuȵ raʾīsuȵ
buʾisa ruʾūfuȵ raʾūfuȵ suʾāluȵ muʾarriḫuȵ
abnāʾa-hu abnāʾu-hu abnāʾi-hi šayʾaȵ ḫaṭīʾaŧuȵ
ḍawʾu-hu ḍūʾu-hu ḍawʾa-hu ḍawʾi-hi murūʾaŧuȵ
ʾabnāʾi-hi barīʾu-hu sūʾila fīluȵ fānnuȵ fūnnuȵ
sāʾala fuʾāduȵ šurakāʾu-hu riʾāsaŧuȵ tahniʾaŧuȵ
dafāʾaŧuȵ ṭaffāʾaŧuȵ taʾrīḫuȵ faʾruȵ
šayʾuȵ šayʾiȵ šayʾaȵ  ḍawʾuȵ ḍawʾiȵ ḍawʾaȵ
ǧuzʾuȵ  ǧuzʾiȵ  ǧuzʾaȵ mabdaʾuȵ mabdaʾiȵ mabdaʾaȵ
nabaʾa ḳāriʾuȵ takāfuʾuȵ takāfuʾiȵ takāfuʾaȵ
abnāʾu abnāʾi abnāʾa ǧarīʾuȵ maḳrūʾuȵ ḍawʾuȵ šayʾuȵ ǧuzʾuȵ
ʿulamāʾu al-ʿulamāʾi al-ʿulamāʾa ʿAmruȵů wa-faʿalūå

### betaCode converted into arabic script

**NB** Formatting below is simply because of the lack of a proper style for Arabic in gitHub 

قَالَ أَبُو مَسْعُودٍ :: أَنَا قَدْ سَمِعْتُ هٰذَا مِنْ رَسُولِ ﭐلـلّٰـهِ ( صْلْعْمْ )

حَدَّثَنَا عَمْرُو بْنُ رَافِعٍ ، حَدَّثَنَا عَبْدُ ﭐلـلّٰـهِ بْنُ ﭐلْمُبَارَكِ ، عَنْ مُحَمَّدِ بْنِ إِسْحَاقَ ، عَنْ مُحَمَّدِ بْنِ جَعْفَرٍ ، عَنْ عُبَيْدِ ﭐلـلّٰـهِ بْنِ عَبْدِ ﭐلـلّٰـهِ بْنِ عُمَرَ ، عَنْ أَبِيهِ ، عَنِ ﭐلنَّبِيِّ ( صْلْعْمْ ) نَحْوَهُ

أَخْبَرَنَا قُتَيْبَةُ قَالَ ، حَدَّثَنَا سُفْيَانُ ، عَنْ يَحْيٰى بْنِ سَعِيدٍ ، عَنْ أَبِي بَكْرِ بْنِ مُحَمَّدٍ ، عَنْ عُمَرَ بْنِ عَبْدِ ﭐلْعَزِيزِ ، عَنْ أَبِي بَكْرِ بْنِ عَبْدِ ﭐلرَّحْمٰنِ بْنِ ﭐلْحَارِثِ بْنِ هِشَامٍ ، عَنْ أَبِي هُرَيْرَةَ مِثْلَهُ

تَحْوِيلُ ﭐلْحَمْزَةِ ( كَلِمَاتٌ مُفْرَدَةٌ )

أَمْرٌ أُنْسٌ إِنْسٌ إِيمَانٌ
آيَةٌ آمَنَ مَسْأَلَةٌ سَأَلَ رَأْسٌ قُرْآنٌ تَآمَرَ
ذِئْبٌ أَسْئِلَةٌ قَارِئِهِ سُؤْلٌ مَسْؤُولٌ
تَكَافُؤُهُ سُئِلَ قَارِئِهِ ذِئَابٌ رَئِيسٌ
بُئِسَ رُؤُوفٌ رَؤُوفٌ سُؤَالٌ مُؤَرِّخٌ
أَبْنَاءَهُ أَبْناؤُهُ أَبْنائِهِ شَيْئًا خَطِيئَةٌ
ضَوْءُهُ ضُوؤُهُ ضَوْءَهُ ضَوْئِهِ مُرُوءَةٌ
أَبْنائِهِ بَرِيؤُهُ سُوئِلَ فِيلٌ فَانٌّ فُونٌّ
سَاءَلَ فُؤَادٌ شُرَكاؤُهُ رِئَاسَةٌ تَهْنِئَةٌ
دَفَاءَةٌ طَفّاءَةٌ تَأْرِيخٌ فَأْرٌ
شَيْءٌ شَيْءٍ شَيْئًا  ضَوْءٌ ضَوْءٍ ضَوْءًا
جُزْءٌ  جُزْءٍ  جُزْءًا مَبْدَأٌ مَبْدَأٍ مَبْدَأً
نَبَأَ قَارِئٌ تَكَافُؤٌ تَكَافُؤٍ تَكَافُؤًا
أَبْناءُ أَبْناءِ أَبْناءَ جَريءٌ مَقْروءٌ ضَوْءٌ شَيْءٌ جُزْءٌ
عُلَماءُ ﭐلْعُلَماءِ ﭐلْعُلَماءَ عَمْرٌو وَفَعَلُوا

## betaCode into Translit

### betaCode in English text

NB: This is an example of the English text with terms, names and toponyms given in betaCode and automatically converted into different transliteration flavors (exerpts are from Brill’s *Encyclopaedia of Islam*).

Dima^s.k, Dima^s.k al-^S\_am or simply al-^S\_am , (Lat. Damascus, Fr. Damas) is the largest city of Syria. It is situated ... very much at the same latitude as Ba.gd\_ad and F\_as, at an altitude of nearly 700 metres, on the edge of the desert at the foot of ^Gabal .K\_asiy\_un.

al-\_Dahab\_i, ^Sams al-D\_in Ab\_u \`Abd All~ah Mu.hammad b. \`U\_tm\_an b. .K\_aym\_a.z b. \`Abd All~ah al-Turkum\_an\_i al-F\_ari.k\_i al-Dima^s.k\_i al-^S\_afi\`\_i, an Arab historian and theologian, was born at Damascus or at Mayy\_afari.k\_in on 1 or 3 Rab\_i\` II (according to al-Kutub\_i, in Rab\_i\` I) 673/5 or 7 October 1274, and died at Damascus, according to al-Subk\_i and al-Suy\_u.t\_i, in the night of Sunday-Monday on 3 \_D\_u al-.Ka\`da:t 748/4 February 1348, or, according to A.hmad b. \`Iy\_as, in 753/1352-3. He was buried at the B\_ab al-.Sa.g\_ir.

### betaCode converted into one-to-one translit

Dimašḳ, Dimašḳ al-Šām or simply al-Šām , (Lat. Damascus, Fr. Damas) is the largest city of Syria. It is situated ... very much at the same latitude as Baġdād and Fās, at an altitude of nearly 700 metres, on the edge of the desert at the foot of Ǧabal Ḳāsiyūn.

al-Ḏahabī, Šams al-Dīn Abū ʿAbd Allãh Muḥammad b. ʿUṯmān b. Ḳāymāẓ b. ʿAbd Allãh al-Turkumānī al-Fāriḳī al-Dimašḳī al-Šāfiʿī, an Arab historian and theologian, was born at Damascus or at Mayyāfariḳīn on 1 or 3 Rabīʿ II (according to al-Kutubī, in Rabīʿ I) 673/5 or 7 October 1274, and died at Damascus, according to al-Subkī and al-Suyūṭī, in the night of Sunday-Monday on 3 Ḏū al-Ḳaʿdaŧ 748/4 February 1348, or, according to Aḥmad b. ʿIyās, in 753/1352-3. He was buried at the Bāb al-Ṣaġīr.

### betaCode converted into the Library of Congress scheme

Dimashq, Dimashq al-Shām or simply al-Shām , (Lat. Damascus, Fr. Damas) is the largest city of Syria. It is situated ... very much at the same latitude as Baghdād and Fās, at an altitude of nearly 700 metres, on the edge of the desert at the foot of Jabal Qāsiyūn.

al-Dhahabī, Shams al-Dīn Abū ʿAbd Allāh Muḥammad b. ʿUthmān b. Qāymāẓ b. ʿAbd Allāh al-Turkumānī al-Fāriqī al-Dimashqī al-Shāfiʿī, an Arab historian and theologian, was born at Damascus or at Mayyāfariqīn on 1 or 3 Rabīʿ II (according to al-Kutubī, in Rabīʿ I) 673/5 or 7 October 1274, and died at Damascus, according to al-Subkī and al-Suyūṭī, in the night of Sunday-Monday on 3 Dhū al-Qaʿda 748/4 February 1348, or, according to Aḥmad b. ʿIyās, in 753/1352-3. He was buried at the Bāb al-Ṣaghīr.

### betaCode converted into a searcheable string (diacritics removed)

Dimashq, Dimashq al-Sham or simply al-Sham , (Lat. Damascus, Fr. Damas) is the largest city of Syria. It is situated ... very much at the same latitude as Baghdad and Fas, at an altitude of nearly 700 metres, on the edge of the desert at the foot of Jabal Qasiyun.

al-Dhahabi, Shams al-Din Abu Abd Allah Muhammad b. Uthman b. Qaymaz b. Abd Allah al-Turkumani al-Fariqi al-Dimashqi al-Shafii, an Arab historian and theologian, was born at Damascus or at Mayyafariqin on 1 or 3 Rabi II (according to al-Kutubi, in Rabi I) 673/5 or 7 October 1274, and died at Damascus, according to al-Subki and al-Suyuti, in the night of Sunday-Monday on 3 Dhu al-Qada 748/4 February 1348, or, according to Ahmad b. Iyas, in 753/1352-3. He was buried at the Bab al-Saghir.
