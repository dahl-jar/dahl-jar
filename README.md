<h1 align="center">Introduction</h1>

<p align="center">
  Most of my projects start with something I want to use myself.<br>
  So far, that has led to a Jellyfin client I sideload onto my iPhone, a C++ app for controlling my PC's RGB hardware, and a k3s cluster running on my own server.
</p>

<h2 align="center">Projects</h2>

<table>
  <tr>
    <td width="50%" valign="top">
      <h3 align="center"><a href="https://github.com/dahl-jar/homeflix-native">Homeflix</a></h3>
      <p>A sideloaded iPhone client for a self-hosted, Jellyfin-compatible media library. It covers library browsing, search, playback preparation, skip segments, native controls, and episode playback.</p>
      <p align="center"><code>React Native</code> <code>Expo</code> <code>Jellyfin API</code></p>
    </td>
    <td width="50%" valign="top">
      <h3 align="center"><a href="https://github.com/dahl-jar/betterreads">BetterReads</a></h3>
      <p>A book tracking platform I rebuilt from an earlier group project. The Spring Boot API combines catalog records from several sources, while the React client handles search, shelves, reviews, and discussions. It runs on k3s through Argo CD.</p>
      <p align="center">
        <a href="https://github.com/dahl-jar/betterreads">Backend</a> ·
        <a href="https://github.com/dahl-jar/betterreads-frontend">Frontend</a> ·
        <a href="https://github.com/dahl-jar/betterreads-gitops-template">GitOps template</a>
      </p>
      <p align="center"><code>Java</code> <code>Spring Boot</code> <code>React</code> <code>TypeScript</code> <code>Postgres</code> <code>Kubernetes</code></p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h3 align="center"><a href="https://github.com/dahl-jar/rgb-picker">RGB Picker</a></h3>
      <p>A Windows app for controlling supported RGB hardware through OpenRGB drivers linked directly into the application. It saves lighting profiles, manages device and zone colors, restores lighting when hardware appears, and includes a command-line client.</p>
      <p align="center"><code>C++23</code> <code>Dear ImGui</code> <code>OpenRGB</code> <code>Win32</code> <code>DirectX 11</code> <code>CMake</code></p>
    </td>
    <td width="50%" valign="top">
      <h3 align="center"><a href="https://github.com/dahl-jar/voice-control">Voice Control</a></h3>
      <p>A hands-free keyboard that maps spoken commands to arrow keys. A small PyTorch model trained on Google Speech Commands v2 handles microphone input locally.</p>
      <p align="center"><code>Python</code> <code>PyTorch</code> <code>TorchAudio</code></p>
    </td>
  </tr>
</table>
