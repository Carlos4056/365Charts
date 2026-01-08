<script lang="ts">
  import MapLayout from "$lib/components/templates/MapLayout.svelte";
  import LocatorMap from "$lib/components/molecules/maps/LocatorMap.svelte";
  import MapBase from "$lib/components/molecules/maps/MapBase.svelte";
  import Legend from "$lib/components/molecules/legends/Legend.svelte";
  import LegendItem from "$lib/components/atoms/items/LegendItem.svelte";
  import ColorRamp from "$lib/components/molecules/legends/ColorRamp.svelte";
  import SizeLegend from "$lib/components/molecules/legends/SizeLegend.svelte";
  import MapLayer from "$lib/utils/MapLayer.svelte";
  
  let mapInstance: any = $state(); 
</script>

<MapLayout>
    <MapBase themeName="GLOBE_3D_GREEN" bind:mapInstance={mapInstance}>
        {#if mapInstance}
            <LocatorMap mainMap={mapInstance} />
        {/if}
    </MapBase>

    <!-- GEOJSON -->
    <!--
    <MapLayer 
        map={mapInstance}
        id="rutes-bicicleta"
        sourceType="geojson"
        type="line"
        data="https://pub-xxxxxxxx.r2.dev/rutes-bici.geojson"
        paint={{
            'line-color': '#ff5722',
            'line-width': 3
        }}
    />-->

    <!-- PMTILES -->

    <!--
    <MapLayer 
        map={mapInstance}
        id="edificis-cat"
        sourceType="vector"
        type="fill-extrusion"
        url="pmtiles://https://pub-xxxxxxxx.r2.dev/edificis-catalunya.pmtiles"
        sourceLayer="edificis" 
        paint={{
            'fill-extrusion-color': '#aaa',
            'fill-extrusion-height': ['get', 'altura']
        }}
    />-->

    <!-- IMAGE -->

    <!--
    <MapLayer 
        map={mapInstance}
        id="mapa-antic-1956"
        sourceType="raster"
        type="raster"
        tiles={['https://pub-xxxxxxxx.r2.dev/1956/{z}/{x}/{y}.png']}
        tileSize={256}
        paint={{
            'raster-opacity': 0.7
        }}
    />-->

    <!-- VIDEO -->
    <!--
    <MapLayer 
        map={mapInstance}
        id="video-ice-melting"
        sourceType="video"
        type="video"
        urls = []
        coordiantes = []
    />-->

    <SizeLegend
      title="Magnitud dels terratremols"
        steps = {[10, 25, 40]}
        labels = {['10', '25', '40']}
        color ="#ff0000"
    ></SizeLegend>          
          

    {#snippet header()}
        <h1>On son les tortugues marines?</h1>
    {/snippet}

    {#snippet description()}
      <p>Aquí fa un temps horrible com sempre, però dins el que seria les temperatures normals</p>
      <!--<Legend title="Risc d'Inundació">
            
            <LegendItem 
                label="PSOE" 
                color="red" 
                type="circle"
            />
            
            <LegendItem 
                label="Zona Inundable (Baix)" 
                color="#ff0000" 
                type="square" 
                variant="outline"
                opacity={0.2} 
            />
            </Legend>-->

            <!--<ColorRamp
              title="Títol de la llegenda" 
              minLabel="0"
              maxLabel="10"
              colors={['#ffeaa7', '#fab1a0', '#ff7675', '#d63031']}
              height = "10px"
            ></ColorRamp>-->

    {/snippet}
    
    {#snippet notes()}
        Font: ICGC | Carlos Albaladejo, 1/365
    {/snippet}

</MapLayout>