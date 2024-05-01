# darktide-maps

json and png for each of the maps currently available in wh40: darktide

The json format is simply:
```
{
 "mission": "{mission id}",
 "1": { -- tile index
      "1": "a.x,a.y,a.z,b.x,b.y,b.z,c.x,c.y,c.z", -- triangle's index, abc are the vertices that make up the triangle
      "size": 1 -- total number of triangles in the tile
 },
 "size": 1 -- total number of tiles in the map
}
```

note: since it comes from lua, indexes are 1 based

The PNGs without a suffix are scaled so that their longest dimension (w/h) is 4k pixels, meaning they aren't at the same scale.
The PNGS ending with _x1, _x5 are scaled by that amount. x1 is 1:1, 1 darktide game world unit (1 meter) to 1 godot 2d unit.

note: the pngs are white with alpha background, so you won't see anything on a white background (like previewing on github)

There is now a {mission id}_size.json file for each mission with the format:
```
{
 "size": "800,400", -- the size in world units of the map
 "offset": "-300,-200" -- the offset in world units that was applied to get the top most and left most vertices to be at the top and left edge of the image
}
```

Mission ids to display names:
```
lm_cooling=Power Matrix HL-17-36
hm_cartel=Vigil Station Oblivium
dm_forge=Smelter Complex HL-17-36
cm_archives=Archivum Sycorax
hm_strain=Refinery Delta-17
km_station=Chasm Station HL-16-11
fm_resurgence=Enclavum Baross
fm_armoury=Mercantile HL-70-04
km_enforcer_twins=The Orthus Offensive
dm_stockpile=Silo Cluster 18-66/a
fm_cargo=Consignment Yard HL-17-36
km_enforcer=Magistrati Oubliette TM8-707
prologue=The Tancred Bastion
cm_habs=Hab Dreyko
hm_complex=Comms-Plex 154/2f
lm_scavenge=Excise Vault Spireside-13
lm_rails=Chasm Logistratum
cm_raid=Warren 6-19
dm_propaganda=Relay Station TRS-150
dm_rise=Ascension Riser 31
```
