# Assignment 1: Make the Apple Fall Realistically 🍎

### Objective
Your goal is to make the Apple prefab fall from a height and bounce realistically using Unity's physics engine.




<div id="game-shell" style="max-width:1100px;margin:0 auto;position:relative;">
  <!-- 16:9 box with no internal scrollbars -->
  <div style="position:relative;width:100%;aspect-ratio:16/9;overflow:hidden;border:0;border-radius:12px;">
    <!-- Cover -->
    <div id="game-cover" style="position:absolute;inset:0;display:flex;align-items:center;justify-content:center;flex-direction:column;background:#111;">
      <!-- Optional: a screenshot thumbnail -->
      <!-- <img src="/path/to/screenshot.jpg" alt="Game cover" style="max-width:100%;height:auto;opacity:.6;"> -->
      <button id="play-btn" style="padding:.8rem 1.2rem;border:0;border-radius:999px;background:#1f6feb;color:#fff;font:600 16px/1.1 system-ui;cursor:pointer;">
        ▶ Play
      </button>
    </div>

    <!-- The game (starts empty; src set on click) -->
    <iframe
      id="game-frame"
      src=""
      title="Game"
      allow="autoplay; fullscreen; gamepad; xr-spatial-tracking"
      allowfullscreen
      scrolling="no"
      frameborder="0"
      style="position:absolute;inset:0;width:100%;height:100%;border:0;overflow:hidden;">
    </iframe>
  </div>

  <!-- Controls row (optional) -->
  <div style="display:flex;gap:.5rem;justify-content:center;margin-top:.5rem;">
    <button id="fs-btn" style="padding:.4rem .8rem;border:1px solid #ccc;border-radius:8px;background:#fff;cursor:pointer;">Fullscreen</button>
  </div>
</div>

<script>
  const PLAY_URL = "{{ site.baseurl }}/webgl/"; // for a project site. For a user/org site use "/webgl/"

  const playBtn = document.getElementById('play-btn');
  const fsBtn   = document.getElementById('fs-btn');
  const frame   = document.getElementById('game-frame');

  playBtn.addEventListener('click', () => {
    frame.src = PLAY_URL;             // loads the Unity page only after click
    document.getElementById('game-cover').style.display = 'none';
    frame.focus();
  });

  fsBtn.addEventListener('click', async () => {
    try {
      // Fullscreen the iframe itself (works as long as allowfullscreen is set)
      if (frame.requestFullscreen) await frame.requestFullscreen();
      else if (frame.webkitRequestFullscreen) frame.webkitRequestFullscreen();
    } catch (e) { console.warn(e); }
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
