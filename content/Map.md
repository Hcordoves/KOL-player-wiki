---
title: World Map
tags: [Map, World]
---

# 🗺 World Map

An interactive map of the Sword Coast and the North — locations the party has visited or learned of during the campaign.

> *The Forgotten Realms, 1508 DR.*

<div id="faerun-map" style="height:580px;width:100%;border-radius:8px;border:1px solid #b8973d;margin:1.5rem 0;"></div>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.min.css"/>
<script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.min.js"></script>

<script>
(function () {
  function initMap() {
      var el = document.getElementById('faerun-map');
          if (!el) { setTimeout(initMap, 150); return; }
              if (el._mapInit) return;
                  el._mapInit = true;
                      var imgW = 2048, imgH = 1448;
                          var map = L.map('faerun-map', {
                                crs: L.CRS.Simple,
                                      minZoom: -2,
                                            maxZoom: 2,
                                                  zoomSnap: 0.5,
                                                        attributionControl: false
                                                            });
                                                                var bounds = [[0, 0], [imgH, imgW]];
                                                                    L.imageOverlay('/Map of Faerun.jpeg', bounds).addTo(map);
                                                                        map.fitBounds(bounds);
                                                                            function dot(color) {
                                                                                  return L.divIcon({
                                                                                          className: '',
                                                                                                  html: '<div style="width:13px;height:13px;border-radius:50%;background:' + color + ';border:2px solid #fff;box-shadow:0 0 5px rgba(0,0,0,.7);"></div>',
                                                                                                          iconAnchor: [6, 6],
                                                                                                                  popupAnchor: [0, -10]
                                                                                                                        });
                                                                                                                            }
                                                                                                                                var pins = [
                                                                                                                                      { name: 'Waterdeep', py: 840, px: 532, color: '#4a8fd4', faction: "Lord's Alliance", note: 'The City of Splendors. A major Alliance stronghold on the Sword Coast.' },
                                                                                                                                            { name: 'Yartar', py: 640, px: 594, color: '#4a8fd4', faction: "Lord's Alliance - Rebuilding", note: 'A river city north of Waterdeep. Recovering from recent conflict.' },
                                                                                                                                                  { name: 'Silverymoon', py: 550, px: 756, color: '#5cb85c', faction: 'Fey Alliance - Occupied', note: 'The Gem of the North, partially destroyed. The North Bank is under Fey Alliance control.' },
                                                                                                                                                        { name: 'High Forest', py: 590, px: 860, color: '#f0ad4e', faction: 'Current Arc', note: "The party's current destination. Deep, vast, and treacherous." }
                                                                                                                                                            ];
                                                                                                                                                                pins.forEach(function (p) {
                                                                                                                                                                      var html = '<div style="min-width:160px;"><strong>' + p.name + '</strong><br><em style="color:#999;font-size:.85em;">' + p.faction + '</em><br><br><span style="font-size:.9em;">' + p.note + '</span></div>';
                                                                                                                                                                            L.marker([imgH - p.py, p.px], { icon: dot(p.color) }).bindPopup(html, { maxWidth: 240 }).addTo(map);
                                                                                                                                                                                });
                                                                                                                                                                                    var legend = L.control({ position: 'bottomright' });
                                                                                                                                                                                        legend.onAdd = function () {
                                                                                                                                                                                              var d = L.DomUtil.create('div');
                                                                                                                                                                                                    d.style.cssText = 'background:rgba(17,16,9,.88);padding:8px 12px;border-radius:6px;border:1px solid #b8973d;font-size:.8em;color:#ddd;line-height:1.9;';
                                                                                                                                                                                                          d.innerHTML = '<strong style="color:#b8973d;">Factions</strong><br><span style="color:#4a8fd4;">&#9679;</span> Lord\'s Alliance<br><span style="color:#5cb85c;">&#9679;</span> Fey Alliance<br><span style="color:#f0ad4e;">&#9679;</span> Active Arc';
                                                                                                                                                                                                                return d;
                                                                                                                                                                                                                    };
                                                                                                                                                                                                                        legend.addTo(map);
                                                                                                                                                                                                                          }
                                                                                                                                                                                                                            if (document.readyState === 'loading') {
                                                                                                                                                                                                                                document.addEventListener('DOMContentLoaded', initMap);
                                                                                                                                                                                                                                  } else { initMap(); }
                                                                                                                                                                                                                                  })();
                                                                                                                                                                                                                                  </script>
                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                  ---
                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                  ## Locations
                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                  ### Sword Coast & The North
                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                  **Waterdeep** - The City of Splendors. The largest city on the Sword Coast, still firmly under Alliance control.
                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                  **Yartar** - A river city on the Surbrin. Recovering from recent conflict. The Alliance is rebuilding its presence here.
                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                  **Silverymoon** - The Gem of the North, now partially destroyed. The North Bank is under the control of King Oberon and Queen Titania of the Fey Alliance.
                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                  **High Forest** - One of the great ancient forests of Faerun. The party's current destination.
                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                  ---
                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                  > Click any marker for details. Map pins are approximate positions.
