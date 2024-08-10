<script lang="ts">
	import TwitchChannelGrid from '$lib/TwitchChannelGrid/TwitchChannelGrid.svelte';

  let channels = [
    'nukadokotaro', 'luluiluu', 'morimoriiiiiii', 'puu3', 'amiya2008', 'nevadatomato', 'darumaramen', 
    'chandy______', 'mimyou', 'kikinene', 'kappy_games', 'shupeso3', 'jooohn15', 'gngn_kosino',
    'hippepen', 'maedatadakatu', 'takajisan', 'eviiiino', 'william_naokichi', 'dezabudzb', 
    'rasi__yattane', 'kassy_games', 'ww_okasama_ww', 'yappy3838', 'komachi_key', 'chiyonog', 
    'okasinokoyanokoya', 'simiryuuu', 'haainico', 'piggyhoggyboo', 'samuraimori3', 'zamurai_japan',
    'kemum4k1', 'orangista12', 'nitroro_', 'dobashi_gengoro', 'wan2tan', 'watawata1218', 'kisetsu_no_mjs',
    'kentoobeta', 'ganbaru_tarou', 'momonoeyumo', 'bal863', 'momotsuyo', 'norishio_42', 'aoiuru_owl', 
    'jerontro_g', 'uninorem', 'gahu3', 'maori215', 'brosutar5v', 'pestalozzi999', 'tashiro_masashi_',
    'tasiota', 'senzsan', 'ryoubeni', 'tenshimoko',
  ];
</script>

<TwitchChannelGrid {channels} />
