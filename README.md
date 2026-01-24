<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0ea5e9,100:22c55e&height=120&section=header&text=✨%20Stargazers%20Analytics&fontSize=30" width="100%" alt="Stargazers Header" />
</p>

<table width="100%">
  <tr>
    <th colspan="2"><h3>📊 Stargazers Evolution & Global Reach</h3></th>
  </tr>
  <tr>
    <td colspan="2" align="center">
      <p>Bu eklenti, projelerine gelen yıldızların zaman içindeki değişimini ve dünya üzerindeki dağılımını görselleştirir.</p>
    </td>
  </tr>
  <tr>
    <th width="30%">🚀 Desteklenen Özellikler</th>
    <td>
      <code>📗 Classic Template</code> • <code>👤 User & Org</code> • <code>📓 Repository</code>
    </td>
  </tr>
  <tr>
    <th width="30%">🔑 Gerekli İzinler</th>
    <td>
      <code>read:user</code> • <code>repo</code> • <code>Google Maps API (Harita için)</code>
    </td>
  </tr>
  <tr>
    <td colspan="2" align="center">
      <br />
      <details open><summary><b>📈 Grafik Görünümü (Classic)</b></summary>
        <a href="https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME/blob/main/metrics.plugin.stargazers.svg">
          <img src="https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME/blob/main/metrics.plugin.stargazers.svg" alt="Classic Chart - Click to view" />
        </a>
      </details>
      
      <details><summary><b>🌐 Dünya Haritası (Worldmap)</b></summary>
        <a href="https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME/blob/main/metrics.plugin.stargazers.worldmap.svg">
          <img src="https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME/blob/main/metrics.plugin.stargazers.worldmap.svg" alt="Worldmap - Click to view" />
        </a>
      </details>
      
      <img width="900" height="1" alt="spacer">
    </td>
  </tr>
</table>
## ➡️ Kullanılabilir Seçenekler (Options)

<table>
  <thead>
    <tr>
      <th>Parametre</th>
      <th>Açıklama</th>
      <th>Varsayılan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>plugin_stargazers</code></td>
      <td>Eklentiyi aktif eder.</td>
      <td><b>no</b></td>
    </tr>
    <tr>
      <td><code>plugin_stargazers_charts_type</code></td>
      <td>Grafik tipi: <code>classic</code> (hafif) veya <code>graph</code> (pürüzsüz).</td>
      <td><b>classic</b></td>
    </tr>
    <tr>
      <td><code>plugin_stargazers_days</code></td>
      <td>Analiz edilecek gün sayısı (0 = hesap açılışından beri).</td>
      <td><b>14</b></td>
    </tr>
    <tr>
      <td><code>plugin_stargazers_worldmap</code></td>
      <td>Yıldız verenlerin dünya haritasını gösterir.</td>
      <td><b>no</b></td>
    </tr>
  </tbody>
</table>

## ℹ️ Örnek Workflow (YAML)

> **Pro Tip:** Eğer dünya haritasını kullanmayacaksan Google Maps token'ına ihtiyacın yok.

```yaml
# 1. Standart Grafik Görünümü
- uses: lowlighter/metrics@latest
  with:
    filename: metrics.plugin.stargazers.svg
    token: ${{ secrets.METRICS_TOKEN }}
    base: ""
    plugin_stargazers: yes
    plugin_stargazers_charts_type: graph

# 2. Dünya Haritası Görünümü (Google Maps API Gerekli)
- uses: lowlighter/metrics@latest
  with:
    filename: metrics.plugin.stargazers.worldmap.svg
    token: ${{ secrets.METRICS_TOKEN }}
    base: ""
    plugin_stargazers: yes
    plugin_stargazers_charts: no
    plugin_stargazers_worldmap: yes
    plugin_stargazers_worldmap_token: ${{ secrets.GOOGLE_MAP_TOKEN }}
