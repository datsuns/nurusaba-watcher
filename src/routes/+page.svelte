<script lang="ts">
  import TwitchChannelGrid from '$lib/TwitchChannelGrid/TwitchChannelGrid.svelte';

  let channels = new Map<string, string>([
    [ 'ぬかどこたろう', 'nukadokotaro' ],
    [ 'るるいチャン', 'luluiluu' ],
    [ 'デザ部のもりもり', 'dezabudzb' ],
    [ 'puu3', 'puu3' ],
    [ '網屋', 'amiya2008' ],
    [ 'ネバダのとまと', 'nevadatomato' ],
    [ 'だるまラーメン', 'darumaramen' ],
    [ 'ちゃんディー', 'chandy______' ],
    [ 'ミミョウ', 'mimyou' ],
    [ 'ききねー', 'kikinene' ],
    [ 'かっぴーげーむす', 'kappy_games' ],
    [ 'しゅぺそ', 'shupeso3' ],
    [ 'じょょょん', 'jooohn15' ],
    [ 'ぐんこしの', 'gngn_kosino' ],
    [ 'ひっぺと申します', 'hippepen' ],
    [ 'けつドレ', 'maedatadakatu' ],
    [ 'たかぢ', 'takajisan' ],
    [ 'えびぃの', 'eviiiino' ],
    [ 'ウィリアムなおきち', 'william_naokichi' ],
    [ 'デザ部のやまやま', 'dezabudzb' ],
    [ 'らっしーやったね', 'rasi__yattane' ],
    [ 'KASSY', 'kassy_games' ],
    [ '岡様', 'ww_okasama_ww' ],
    [ 'やっぴーちゃんねる', 'yappy3838' ],
    [ '調子こきまろのこまち', 'komachi_key' ],
    [ 'ちよん', 'chiyonog' ],
    [ 'お菓子の小屋', 'okasinokoyanokoya' ],
    [ 'しみりゅー', 'simiryuuu' ],
    [ '太陽神灰にこ', 'haainico' ],
    [ 'PiggyHoggyBoo', 'piggyhoggyboo' ],
    [ 'もりさん', 'samuraimori3' ],
    [ 'ないん', 'ty9nine' ],
    [ 'ざむらいジャパン', 'zamurai_japan' ],
    [ '煙巻', 'kemum4k1' ],
    [ 'たくぷー', 'orangista12' ],
    [ 'にとろろ', 'nitroro_' ],
    [ 'どばし校長', 'dobashi_gengoro' ],
    [ 'ワンたん', 'wan2tan' ],
    [ 'わた軍団', 'watawata1218' ],
    [ 'もりぶでん', 'moribuden_seseri' ],
    [ '季節の饅頭を添えたい', 'kisetsu_no_mjs' ],
    [ 'ケントゥベータ', 'kentoobeta' ],
    [ 'ガンバルタロウ', 'ganbaru_tarou' ],
    [ '桃枝ゆも', 'momonoeyumo' ],
    [ '普通のばる', 'bal863' ],
    [ 'パンツマン', 'momotsuyo' ],
    [ 'あおちゃん', 'aotadado' ],
    [ 'Norishio42', 'norishio_42' ],
    [ '葵うる', 'aoiuru_owl' ],
    [ '天使㋲子', 'tenshimoko' ],
    [ 'ぢぇろ', 'jerontro_g' ],
    [ 'うにのれむ', 'uninorem' ],
    [ 'くま沢ガフ美', 'gahu3' ],
    [ 'おきつね杏ちゃん', 'maori215' ],
    [ 'Tm-woody', 'tmwooody' ],
    [ '女装のブロスター', 'brosutar5v' ],
    [ 'pestalozzi999', 'pestalozzi999' ],
    [ '田代まさし', 'tashiro_masashi_' ],
    [ 'たしおた', 'tasiota' ],
    [ 'せんず', 'senzsan' ],
    [ 'ryoubeni', 'ryoubeni' ],

  ]);
</script>

<TwitchChannelGrid {channels} />
