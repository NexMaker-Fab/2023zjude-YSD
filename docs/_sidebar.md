<div>
  <img src="https://github.com/erkoww/YSD_img/blob/main/img/1ogo.png?raw=true" width="200"/>
</div>

<div class="sidebar">
  <h2 onclick="toggleSection('team')">TEAM INTRODUCE</h2>
  <div id="team" class="section">
    <ul>
      <li><a href="teamintro.md">Team Introduction</a></li>
      <li><a href="FYJ.md">Feng Yujuan ๑ᵒᯅᵒ๑</a></li>
      <li><a href="GKW.md">Guo Kewei| ᐕ)⁾⁾</a></li>
      <li><a href="LY.md">Lu Yue ⌓‿⌓</a></li>
      <li><a href="WSY.md">Wang Shuyi oi-io</a></li>
      <li><a href="ZKY.md">Zhao Kayu !_!</a></li>
    </ul>
  </div>

  <h2 onclick="toggleSection('course')">COURSE PRACTICE</h2>
  <div id="course" class="section">
    <ul>
      <li><a href="_webbuild.md">Project Management - Web Page Construction</a></li>
      <li><a href="_fusion360.md">CAD - Fusion 360</a></li>
      <li><a href="_arduino_basic.md">Arduino - Arduino Basic</a></li>
      <li><a href="_arduino_input_output.md">Arduino - Arduino Input & Output</a></li>
      <li><a href="_Banbu.md">3D Printing - Banbu</a></li>
    </ul>
  </div>

  <h2 onclick="toggleSection('final')">FINAL PROJECT</h2>
  <div id="final" class="section">
    <ul>
      <li><a href="_concept.md">Final Project - Initial Concept</a></li>
    </ul>
  </div>
</div>

<script>
  function toggleSection(sectionId) {
    const section = document.getElementById(sectionId);
    section.classList.toggle('active');
  }
</script>

<style>
  .section {
    display: none;
  }

  .section.active {
    display: block;
  }
</style>
