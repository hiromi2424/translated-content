---
title: Window.mozAnimationStartTime
slug: Web/API/Animation/startTime
tags:
  - API
  - HTML DOM
  - Obsolete
  - Propriété
  - Reference
  - Window
translation_of: Web/API/Window/mozAnimationStartTime
original_slug: Web/API/Window/mozAnimationStartTime
---
<p>{{APIRef("Mozilla Extensions")}}{{Non-standard_Header}}{{Obsolete_Header("Gecko42")}}</p>

<p>Renvoie l'heure, en millisecondes depuis l'époque, à laquelle les animations ont commencé maintenant doivent être considérées comme ayant commencé. Cette valeur doit être utilisée à la place, par exemple, <code><a href="/en/JavaScript/Reference/Global_Objects/Date/now">Date.now()</a></code>, car cette valeur sera la même pour toutes les animations lancées dans cette fenêtre pendant cet intervalle d'actualisation, leur permettant de rester synchronisées les unes avec les autres.</p>

<p>Cela permet également aux animations basées sur JavaScript de rester synchronisées avec les transitions CSS et les animations SMIL déclenchées pendant le même intervalle d'actualisation.</p>

<h2 id="Syntax">Syntaxe</h2>

<pre class="eval"><em>time</em> = window.mozAnimationStartTime;
</pre>

<h3 id="Parameters">Paramètres</h3>

<ul>
 <li><em><code>time</code></em> est le temps en millisecondes depuis l'époque à laquelle les animations de la fenêtre actuelle doivent être considérées comme ayant démarré.</li>
</ul>

<h2 id="Compatibilité_des_navigateurs">Compatibilité des navigateurs</h2>

<p>{{Compat("api.Window.mozAnimationStartTime")}}</p>

<h2 id="Voir_également">Voir également</h2>

<ul>
 <li>{{domxref("window.mozRequestAnimationFrame()")}}</li>
 <li>{{domxref("window.onmozbeforepaint")}}</li>
</ul>