# Credits

## Assets

- `assets/3d/` (stil-3d, 23.11.2026): the stylized 3D chibi look of the game's song video.
  - `gokyuzu.webp`: the painted dusk sky over Istanbul behind the roofs. Generated with Microsoft Copilot
    (text prompt), 1536x1024.
  - `yakalandi.webp`: the apprentice girl holding the ring up, the cat sulking (level result card). Generated with
    Microsoft Copilot (text prompt), downscaled to 560 px.
  - `baslik.webp` (title card), `ikili.webp` (ending and endless cards) and `kedi-ikon.webp` (HUD icon): crops of the
    song video's own key frames (`muzik-reel/oyunlar/carsi-kacisi/gorsel/genis.jpg`, `kiz_kart.jpg`, made with
    Flow / Nano Banana Pro for the video), downscaled.
  - All are hidden or not loaded with `?noassets`.
- `assets/mascot/kedi-tamam.png` and `assets/mascot/kedi-kutlama.png`: the white Turkish Van kitten mascot of the
  Claude Game Arena, downscaled to 256 px from the author's own copies in the video studio (`kedi-tamam.png`,
  `kedi-kutlama.png`). No longer shown since stil-3d (the cards show the song video's characters); kept in the repo.

## Code and libraries

- Three.js r170, loaded from cdn.jsdelivr.net (MIT licence, https://threejs.org/).
- Everything else (levels, models, textures, sounds and the bazaar scene) is generated in `index.html`. Since stil-3d
  the runner and the cat are soft chibi models of the song video's characters (the apprentice girl and the orange
  tabby), lit with standard materials instead of cel shading and ink outlines.
