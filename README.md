# Assignment 1: Make the Apple Fall Realistically 🍎

### Objective
Your goal is to make the Apple prefab fall from a height and bounce realistically using Unity's physics engine.

<div id="game-shell" style="max-width:1100px;margin:0 auto;position:relative;">
  <div style="position:relative;width:100%;aspect-ratio:16/9;overflow:hidden;border-radius:12px;">
    <!-- Cover -->
    <div id="game-cover" style="position:absolute;inset:0;display:flex;align-items:center;justify-content:center;gap:12px;background:#111;z-index:1;">
      <button id="play-btn" style="padding:.85rem 1.25rem;border:0;border-radius:999px;background:#1f6feb;color:#fff;font:600 16px system-ui;cursor:pointer;">
        ▶ Play
      </button>
    </div>

    <!-- The game iframe (stays empty until click, so no auto-run) -->
    <iframe
      id="game-frame"
      title="Game"
      allow="autoplay; fullscreen; gamepad; xr-spatial-tracking"
      allowfullscreen
      scrolling="no"
      frameborder="0"
      style="position:absolute;inset:0;width:100%;height:100%;border:0;overflow:hidden;">
    </iframe>
  </div>

  <!-- Optional fullscreen button under the frame -->
  <div style="display:flex;gap:.5rem;justify-content:center;margin-top:.5rem;">
    <button id="fs-btn" style="padding:.45rem .8rem;border:1px solid #ccc;border-radius:8px;background:#fff;cursor:pointer;">
      Fullscreen
    </button>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', () => {
  // Use an ABSOLUTE URL so Jekyll/baseurl quirks don't break it.
  // Project site (https://YOUR_USERNAME.github.io/YOUR_REPO/webgl/):
  const PLAY_URL = "{{ site.baseurl }}/webgl/";
  // If this is a USER/ORG site instead, use this instead:
  // const PLAY_URL = "https://YOUR_USERNAME.github.io/webgl/";

  const frame = document.getElementById('game-frame');
  const cover = document.getElementById('game-cover');

  document.getElementById('play-btn').addEventListener('click', () => {
    frame.src = PLAY_URL;        // load Unity only after click
    cover.style.display = 'none';
    frame.focus();
  });

  document.getElementById('fs-btn').addEventListener('click', async () => {
    try {
      if (frame.requestFullscreen) await frame.requestFullscreen();
      else if (frame.webkitRequestFullscreen) frame.webkitRequestFullscreen();
    } catch (e) {
      console.warn('Fullscreen failed:', e);
    }
  });
});
</script>



### Steps
1. Open `Assets/Scenes/AppleScene.unity`.
2. Select the Apple prefab in the scene.
3. Add a Rigidbody component.
4. Adjust mass, drag, and collider settings for realism.
5. Make the apple fall and bounce once.
6. (Optional) Add ground friction or material.

### Deliverables
- Your modified Unity scene and assets (push them via GitHub).
- Optional: Include a screenshot or short video showing the apple falling.
- Optionally explain what you changed in this README file.

> Make sure to test the behavior in Play mode before submission!
