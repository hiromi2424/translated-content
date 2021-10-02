---
title: window
slug: Web/API/Window
tags:
  - API
  - DOM
  - Interface
  - JavaScript
  - Reference
  - Window
translation_of: Web/API/Window
---
<p>{{APIRef}}</p>

<p>L'objet <code>window</code> représente une fenêtre contenant un document DOM ; la propriété <code>document</code> pointe vers le <a href="/fr-FR/docs/DOM/document">document DOM</a> chargé dans cette fenêtre. Une fenêtre pour un document donné peut être obtenue en utilisant la propriété {{Domxref("document.defaultView")}}.</p>

<p>Cette section fournit une brève référence pour toutes les méthodes, propriétés et événements disponibles via l'objet DOM <code>window</code>. L'objet <code>window</code> implémente l'interface <code>Window</code>, qui à son tour hérite de l'interface <code><a href="http://www.w3.org/TR/DOM-Level-2-Views/views.html#Views-AbstractView">AbstractView</a></code>. Certaines fonctions globales supplémentaires, espaces de noms, objets, interfaces et constructeurs, non typiquement associés à la fenêtre, mais disponibles sur celle-ci, sont répertoriés dans la <a href="/fr-FR/docs/JavaScript/Reference">Référence JavaScript</a> et la <a href="/fr-FR/docs/Web/API/Document_Object_Model">Référence DOM</a>.</p>

<p>Dans un navigateur utilisant des onglets, comme Firefox, chaque onglet contient son propre objet <code>window</code> (et si vous écrivez une extension, la fenêtre du navigateur elle-même est un objet <code>window</code> séparé — consultez <a href="/fr/docs/Mozilla/Working_with_windows_in_chrome_code#Fen.C3.AAtres_de_contenu">Travailler avec des fenêtres dans du code chrome</a> pour plus d'informations). C'est-à-dire que l'objet <code>window</code> n'est pas partagé entre les onglets dans la même fenêtre. Certaines méthodes, notamment {{ Domxref("window.resizeTo") }} et {{ Domxref("window.resizeBy") }}, s'appliquent à la fenêtre entière et non à l'onglet spécifique auquel l'objet <code>window</code> appartient. En général, ce qui ne peut raisonnablement pas concerner un onglet se rapporte à la fenêtre à la place.</p>

<p>{{InheritanceDiagram}}</p>

<h2 id="Propriétés">Propriétés</h2>

<p><em>Cette interface hérite des propriétés de l'interface {{domxref("EventTarget")}} et implémente les propriétés des mixins {{domxref("WindowOrWorkerGlobalScope")}} et {{domxref("WindowEventHandlers")}}.</em></p>

<p>Notez que les propriétés qui sont des objets (par exemple, pour redéfinir le prototype d'éléments intrinsèques) sont répertoriées dans une section distincte ci-dessous.</p>

<dl>
 <dt>{{domxref("Window.closed")}} {{Non-standard_inline}}{{readOnlyInline}}</dt>
 <dd>Cette propriété indique si la fenêtre en cours est fermée ou non.</dd>
 <dt>{{domxref("Window.console")}} {{ReadOnlyInline}}</dt>
 <dd>Renvoie une référence à l'objet console qui fournit l'accès à la console de débogage du navigateur.</dd>
 <dt>{{domxref("Window.content")}} et <code>Window._content</code> {{Non-standard_inline}} {{obsolete_inline}}{{ReadOnlyInline}}</dt>
 <dd>Renvoie une référence à l'élément de contenu dans la fenêtre en cours. Depuis Firefox 57 (initialement Nightly uniquement), les deux versions sont uniquement disponibles à partir du code chrome (privilégié) et ne sont plus disponibles sur le Web.</dd>
 <dt>{{domxref("Window.controllers")}}{{non-standard_inline}}{{ReadOnlyInline}}</dt>
 <dd>Renvoie les objets du contrôleur XUL pour la fenêtre chrome en cours.</dd>
 <dt>{{domxref("Window.customElements")}}{{ReadOnlyInline}}</dt>
 <dd>renvoie une référence à l'objet {{domxref("CustomElementRegistry")}}, qui peut être utilisée pour enregistrer de nouveaux <a href="/fr-FR/docs/Web/Web_Components/Using_custom_elements">éléments personnalisés</a> et obtenir des informations à propos d'éléments personnalisés précédemment enregistrés.</dd>
 <dt>{{domxref("Window.crypto")}} {{readOnlyInline}}</dt>
 <dd>Retourne l'objet crypto du navigateur.</dd>
 <dt>{{domxref("Window.defaultStatus")}} {{Obsolete_inline("gecko23")}}</dt>
 <dd>Récupère / définit le texte de la barre d'état pour la fenêtre donnée.</dd>
 <dt>{{domxref("Window.devicePixelRatio")}} {{non-standard_inline}}{{ReadOnlyInline}}</dt>
 <dd>Renvoie le rapport entre les pixels physiques et les pixels indépendants du périphérique dans l'affichage en cours.</dd>
 <dt>{{domxref("Window.dialogArguments")}} {{ReadOnlyInline}}</dt>
 <dd>Récupère les arguments passés à la fenêtre (si c'est une boîte de dialogue) au moment où {{domxref ("window.showModalDialog()")}} a été appelé. C'est un {{Interface("nsIArray")}}.</dd>
 <dt>{{domxref("Window.directories")}} {{obsolete_inline}}</dt>
 <dd>Synonyme de {{domxref("window.personalbar")}}</dd>
 <dt>{{domxref("Window.document")}} {{ReadOnlyInline}}</dt>
 <dd>Renvoie une référence au document que la fenêtre contient.</dd>
 <dt>{{domxref("Window.DOMMatrix")}} {{readOnlyInline}} {{experimental_inline}}</dt>
 <dd>Renvoie une référence à un objet {{domxref("DOMMatrix")}} représentant des matrices 4x4, adapté aux opérations 2D et 3D.</dd>
 <dt>{{domxref("Window.DOMMatrixReadOnly")}} {{readOnlyInline}} {{experimental_inline}}</dt>
 <dd>Renvoie une référence à un objet {{domxref("DOMMatrixReadOnly")}} représentant des matrices 4x4, adapté aux opérations 2D et 3D.</dd>
 <dt>{{domxref("Window.DOMPoint")}} {{readOnlyInline}} {{experimental_inline}}</dt>
 <dd>Renvoie une référence à un objet {{domxref("DOMPoint")}} représentant un point 2D ou 3D dans un système de coordonnées.</dd>
 <dt>{{domxref("Window.DOMPointReadOnly")}} {{readOnlyInline}} {{experimental_inline}}</dt>
 <dd>Renvoie une référence à un objet {{domxref("DOMPointReadOnly")}} représentant un point 2D ou 3D dans un système de coordonnées.</dd>
 <dt>{{domxref("Window.DOMQuad")}} {{readOnlyInline}} {{experimental_inline}}</dt>
 <dd>Renvoie une référence à un objet {{domxref("DOMQuad")}}, qui fournit un objet quadrilatère, c'est-à-dire, ayant quatre coins et quatre côtés.</dd>
 <dt>{{domxref("Window.DOMRect")}} {{readOnlyInline}} {{experimental_inline}}</dt>
 <dd>Returns a reference to a {{domxref("DOMRect")}} object, which represents a rectangle.</dd>
 <dt>{{domxref("Window.DOMRectReadOnly")}} {{readOnlyInline}} {{experimental_inline}}</dt>
 <dd>Renvoie une référence à un objet {{domxref("DOMRectReadOnly")}} représentant un rectangle.</dd>
 <dt>{{domxref("Window.frameElement")}} {{readOnlyInline}}</dt>
 <dd>Renvoie l'élément dans lequel la fenêtre est intégrée, ou null si la fenêtre n'est pas intégrée.</dd>
 <dt>{{domxref("Window.frames")}} {{readOnlyInline}}</dt>
 <dd>Renvoie un tableau des sous-cadres dans la fenêtre en cours.</dd>
 <dt>{{domxref("Window.fullScreen")}} {{gecko_minversion_inline("1.9")}}</dt>
 <dd>Cette propriété indique si la fenêtre est affichée en plein écran ou non.</dd>
 <dt>{{domxref("Window.globalStorage")}} {{gecko_minversion_inline("1.8.1")}} {{Non-standard_inline}} {{Obsolete_inline("gecko13")}}</dt>
 <dd>Non supporté depuis Gecko 13 (Firefox 13). Utilisez {{domxref("Window.localStorage")}} à la place.<br>
 Était : divers objets de stockage utilisés pour stocker des données sur plusieurs pages.</dd>
 <dt>{{domxref("Window.history")}} {{ReadOnlyInline}}</dt>
 <dd>Retourne une référence à l'objet d'historique.</dd>
 <dt>{{domxref("Window.innerHeight")}} {{readOnlyInline}}</dt>
 <dd>Récupère la hauteur de la zone de contenu de la fenêtre du navigateur, y compris, si affichée, la barre de défilement horizontale.</dd>
 <dt>{{domxref("Window.innerWidth")}} {{readOnlyInline}}</dt>
 <dd>Récupère la largeur de la zone de contenu de la fenêtre du navigateur, y compris, si affichée, la barre de défilement verticale.</dd>
 <dt>{{domxref("Window.isSecureContext")}} {{readOnlyInline}}</dt>
 <dd>Indique si un contexte est capable d'utiliser des fonctionnalités nécessitant des contextes sécurisés.</dd>
 <dt>{{domxref("Window.length")}} {{readOnlyInline}}</dt>
 <dd>Renvoie le nombre de cadres dans la fenêtre. Voir également {{domxref("window.frames")}}.</dd>
 <dt>{{domxref("Window.location")}}</dt>
 <dd>Récupère/définit l'emplacement, ou l'URL en cours, de l'objet de fenêtre.</dd>
 <dt>{{domxref("Window.locationbar")}} {{ReadOnlyInline}}</dt>
 <dd>Renvoie l'objet de la barre d'adresse, dont la visibilité peut être inversée dans la fenêtre.</dd>
 <dt>{{domxref("Window.localStorage")}} {{readOnlyInline}}{{gecko_minversion_inline("1.9.1")}}</dt>
 <dd>Renvoie une référence à l'objet de stockage local utilisé pour stocker les données accessibles uniquement par l'origine qui les a créées.</dd>
 <dt>{{domxref("Window.menubar")}} {{ReadOnlyInline}}</dt>
 <dd>Renvoie l'objet barre de menus, dont la visibilité peut être inversée dans la fenêtre.</dd>
 <dt>{{domxref("Window.messageManager")}} {{gecko_minversion_inline("2.0")}}</dt>
 <dd>Renvoie l'objet <a href="/fr-FR/docs/The_message_manager">gestionnaire de messages</a> pour cette fenêtre.</dd>
 <dt>{{domxref("Window.mozAnimationStartTime")}} {{ReadOnlyInline}}{{gecko_minversion_inline("2.0")}} {{Deprecated_inline}}</dt>
 <dd>Le temps en millisecondes depuis l'instant auquel le cycle d'animation en cours a commencé.</dd>
 <dt>{{domxref("Window.mozInnerScreenX")}} {{ReadOnlyInline}}{{non-standard_inline}}{{gecko_minversion_inline("1.9.2")}}</dt>
 <dd>Renvoie la coordonnée horizontale (X) du coin supérieur gauche du point de vue de la fenêtre, en coordonnées d'écran. Cette valeur est restituée en pixels CSS. Voir <code>mozScreenPixelsPerCSSPixel</code> dans {{interface("nsIDOMWindowUtils")}} pour un facteur de conversion pour s'adapter aux pixels de l'écran si nécessaire.</dd>
 <dt>{{domxref("Window.mozInnerScreenY")}} {{ReadOnlyInline}} {{non-standard_inline}}{{gecko_minversion_inline("1.9.2")}}</dt>
 <dd>Renvoie la coordonnée verticale (Y) du coin supérieur gauche du point de vue de la fenêtre, en coordonnées d'écran. Cette valeur est indiquée en pixels CSS. Voir <code>mozScreenPixelsPerCSSPixel</code> pour un facteur de conversion pour s'adapter aux pixels de l'écran si nécessaire.</dd>
 <dt>{{domxref("Window.mozPaintCount")}} {{non-standard_inline}}{{ReadOnlyInline}} {{gecko_minversion_inline("2.0")}}</dt>
 <dd>Renvoie le nombre de fois où le document en cours a été réaffiché à l'écran dans cette fenêtre. Cela peut être utilisé pour calculer les performances d'affichage.</dd>
 <dt>{{domxref("Window.name")}}</dt>
 <dd>Récupère / définit le nom de la fenêtre.</dd>
 <dt>{{domxref("Window.navigator")}} {{readOnlyInline}}</dt>
 <dd>Renvoie une référence à l'objet navigateur.</dd>
 <dt>{{domxref("Window.NetworkInformation")}} {{readOnlyInline}} {{experimental_inline}}</dt>
 <dd>Renvoie une référence à l'interface {{domxref("NetworkInformation")}}, qui fournit des informations sur la connexion qu'un périphérique est en train d'utiliser pour communiquer avec le réseau et fournit un moyen pour les scripts d'être notifiés si le type de connexion change. </dd>
 <dt>{{domxref("Window.opener")}}</dt>
 <dd>Renvoie une référence à la fenêtre qui a ouvert la fenêtre en cours.</dd>
 <dt>{{domxref("Window.orientation")}}{{non-standard_inline}}{{deprecated_inline}}{{readOnlyInline}}</dt>
 <dd>Renvoie l'orientation en degrés (par incréments de 90 degrés) du point de vue par rapport à l'orientation naturelle du périphérique.</dd>
 <dt>{{domxref("Window.outerHeight")}} {{readOnlyInline}}</dt>
 <dd>Récupère la hauteur de l'extérieur de la fenêtre du navigateur.</dd>
 <dt>{{domxref("Window.outerWidth")}} {{readOnlyInline}}</dt>
 <dd>Récupère la largeur de l'extérieur de la fenêtre du navigateur.</dd>
 <dt>{{domxref("Window.scrollX","Window.pageXOffset")}} {{readOnlyInline}}</dt>
 <dd>Un alias pour {{domxref("window.scrollX")}}.</dd>
 <dt>{{domxref("Window.scrollY","Window.pageYOffset")}}{{readOnlyInline}}</dt>
 <dd>Un alias pour {{domxref("window.scrollY")}}</dd>
 <dt>{{domxref("Window.sessionStorage")}} {{readOnlyInline}}</dt>
 <dd>Renvoie une référence à l'objet de stockage de session utilisé pour stocker les données accessibles uniquement par l'origine qui les a créées..</dd>
 <dt>{{domxref("Window.parent")}} {{readOnlyInline}}</dt>
 <dd>Renvoie une référence au parent de la fenêtre ou du sous-cadre en cours.</dd>
 <dt>{{domxref("Window.performance")}} {{readOnlyInline}}</dt>
 <dd>Renvoie un objet {{domxref("Performance")}}, qui inclut les attributs {{domxref("Performance.timing", "timing")}} et {{domxref("Performance.navigation", "navigation")}}, dont chacun est un objet fournissant des données liées aux performances. Voir aussi <a href="/fr-FR/docs/Web/API/Navigation_timing_API/Using_Navigation_Timing">Utilisation de Chronométrage de Navigation</a> pour plus d'informations et d'exemples.</dd>
 <dt>{{domxref("Window.personalbar")}} {{readOnlyInline}}</dt>
 <dd>Renvoie l'objet barre personnelle, dont la visibilité peut être inversée dans la fenêtre.</dd>
 <dt>{{domxref("Window.pkcs11")}} {{obsolete_inline(29)}}</dt>
 <dd>Fournissait précédemment un accès pour installer et supprimer des modules PKCS11.</dd>
 <dt>{{domxref("Window.returnValue")}}</dt>
 <dd>La valeur de retour à renvoyer à la fonction qui a appelé {{domxref("window.showModalDialog()")}} pour afficher la fenêtre comme boîte de dialogue modale.</dd>
 <dt>{{domxref("Window.screen")}} {{readOnlyInline}}</dt>
 <dd>Renvoie une référence à l'objet écran associé à la fenêtre.</dd>
 <dt>{{domxref("Window.screenX")}} {{readOnlyInline}}</dt>
 <dd>Renvoie la distance horizontale de la bordure gauche du navigateur de l'utilisateur à partir du côté gauche de l'écran.</dd>
 <dt>{{domxref("Window.screenY")}} {{readOnlyInline}}</dt>
 <dd>Renvoie la distance verticale de la bordure supérieure du navigateur de l'utilisateur à partir du haut de l'écran.</dd>
 <dt>{{domxref("Window.scrollbars")}} {{readOnlyInline}}</dt>
 <dd>Renvoie l'objet barres de défilement, dont la visibilité peut être modifiée dans la fenêtre.</dd>
 <dt>{{domxref("Window.scrollMaxX")}}{{non-standard_inline}}{{ReadOnlyInline}}</dt>
 <dd>Le décalage maximal dont la fenêtre peut étre décalée horizontalement, c'est-à-dire la largeur du document moins la largeur du point de vue.</dd>
 <dt>{{domxref("Window.scrollMaxY")}}{{non-standard_inline}}{{ReadOnlyInline}}</dt>
 <dd>Le décalage maximal dont la fenêtre peut étre décalée verticalement (c'est-à-dire, la hauteur du document moins la hauteur du point de vue).</dd>
 <dt>{{domxref("Window.scrollX")}} {{readOnlyInline}}</dt>
 <dd>Renvoie le nombre de pixels dont le document a déjà été décalé horizontalement.</dd>
 <dt>{{domxref("Window.scrollY")}} {{readOnlyInline}}</dt>
 <dd>Renvoie le nombre de pixels dont le document a déjà été décalé verticalement.</dd>
 <dt>{{domxref("Window.self")}} {{ReadOnlyInline}}</dt>
 <dd>Renvoie une référence d'objet à l'objet fenêtre lui-même.</dd>
 <dt>{{domxref("Window.sessionStorage")}}</dt>
 <dd>Renvoie un objet de stockage pour stocker des données dans une session de page unique.</dd>
 <dt>{{domxref("Window.sidebar")}} {{non-standard_inline}}{{ReadOnlyInline}}</dt>
 <dd>Renvoie une référence à l'objet fenêtre de la barre latérale.</dd>
 <dt>{{domxref("Window.speechSynthesis")}} {{ReadOnlyInline}}</dt>
 <dd>Renvoie un objet {{domxref("SpeechSynthesis")}}, qui est le point d'entrée pour l'utilisation de la fonctionnalité de synthèse vocale de l'<a href="/fr-FR/docs/Web/API/Web_Speech_API">API Web Speech</a>.</dd>
 <dt>{{domxref("Window.status")}}</dt>
 <dd>Récupère/définit le texte dans la barre d'état en bas du navigateur.</dd>
 <dt>{{domxref("Window.statusbar")}} {{readOnlyInline}}</dt>
 <dd>Renvoie l'objet barre d'état, dont la visibilité peut être inversée dans la fenêtre.</dd>
 <dt>{{domxref("Window.toolbar")}} {{readOnlyInline}}</dt>
 <dd>Renvoie l'objet barre d'outils, dont la visibilité peut être inversée dans la fenêtre.</dd>
 <dt>{{domxref("Window.top")}} {{readOnlyInline}}</dt>
 <dd>Renvoie une référence à la fenêtre la plus haute dans la hiérarchie des fenêtres. Cette propriété est en lecture seule.</dd>
 <dt>{{domxref("Window.visualViewport")}} {{readOnlyInline}}</dt>
 <dd>Renvoie un objet {{domxref("VisualViewport")}} représentant le point de vue visuel pour une fenêtre donnée.</dd>
 <dt>{{domxref("Window.window")}} {{ReadOnlyInline}}</dt>
 <dd>Renvoie une référence à la fenêtre en cours.</dd>
 <dt><code>window[0]</code>,<code> window[1]</code>, etc.</dt>
 <dd>Renvoie une référence à l'objet <code>window</code> dans les cadres. Voir {{domxref("Window.frames")}}} pour plus de détails.</dd>
</dl>

<h3 id="Propriétés_implémentées_depuis_ailleurs">Propriétés implémentées depuis ailleurs</h3>

<dl>
 <dt>{{domxref("WindowOrWorkerGlobalScope.caches")}} {{readOnlyinline}}</dt>
 <dd>Renvoie l'objet {{domxref("CacheStorage")}} associé au contexte en cours. Cet objet active des fonctionnalités telles que le stockage des ressources pour une utilisation hors connexion, et la génération de réponses personnalisées aux requêtes.</dd>
 <dt>{{domxref("WindowOrWorkerGlobalScope.indexedDB")}} {{readonlyInline}}</dt>
 <dd>Fournit un mécanisme permettant aux applications d'accéder de manière asynchrone à des bases de données indexées ; renvoie un objet {{domxref("IDBFactory")}}.</dd>
 <dt>{{domxref("WindowOrWorkerGlobalScope.isSecureContext")}} {{readOnlyinline}}</dt>
 <dd>Renvoie un booléen indiquant si le contexte actuel est sécurisé (<code>true</code>) ou non (<code>false</code>).</dd>
 <dt>{{domxref("WindowOrWorkerGlobalScope.origin")}} {{readOnlyinline}}</dt>
 <dd>Renvoie l'origine de l'objet global, sérialisé comme une chaîne. (Cela ne semble pas encore être implémenté dans aucun navigateur.)</dd>
</dl>

<h2 id="M.C3.A9thodes">Méthodes</h2>

<p><em>Cette interface hérite des méthodes de l'interface {{domxref("EventTarget")}} et implémente les méthodes de {{domxref("WindowOrWorkerGlobalScope")}} et {{domxref("EventTarget")}}.</em></p>

<dl>
 <dt>{{domxref("Window.alert()")}}</dt>
 <dd>Affiche une boîte de message d'alerte.</dd>
 <dt>{{domxref("Window.back()")}} {{Non-standard_inline}} {{obsolete_inline}}</dt>
 <dd>Recule d'une page dans l'historique de la fenêtre.</dd>
 <dt>{{domxref("Window.blur()")}}</dt>
 <dd>Déplace la focalisation hors de la fenêtre.</dd>
 <dt>{{domxref("Window.cancelAnimationFrame()")}} {{experimental_inline}}</dt>
 <dd>Vous permet d'annuler un rappel précédemment planifié avec {{domxref("Window.requestAnimationFrame")}}.</dd>
 <dt>{{domxref("Window.cancelIdleCallback()")}} {{experimental_inline}}</dt>
 <dd>Vous permet d'annuler un rappel précédemment planifié avec {{domxref("Window.requestIdleCallback")}}.</dd>
 <dt>{{domxref("Window.captureEvents()")}} {{Deprecated_inline}}</dt>
 <dd>Enregistre la fenêtre pour qu'elle capture tous les évènements du type spécifié.</dd>
 <dt>{{domxref("Window.clearImmediate()")}}</dt>
 <dd>Annule l'exécution répétée définie en utilisant <code>setImmediate</code>.</dd>
 <dt>{{domxref("Window.close()")}}</dt>
 <dd>Ferme la fenêtre en cours.</dd>
 <dt>{{domxref("Window.confirm()")}}</dt>
 <dd>Affiche une boîte de dialogue avec un message auquel l'utilisateur doit répondre.</dd>
 <dt>{{domxref("Window.disableExternalCapture()")}} {{obsolete_inline(24)}}</dt>
 <dd>{{todo("NeedsContents")}}</dd>
 <dt>{{domxref("Window.dispatchEvent()")}}</dt>
 <dd>Utilisé pour déclencher un évènement.</dd>
 <dt>{{domxref("Window.dump()")}} {{Non-standard_inline}}</dt>
 <dd>Écrit un message à la console.</dd>
 <dt>{{domxref("Window.enableExternalCapture()")}} {{obsolete_inline(24)}}</dt>
 <dd>{{todo("NeedsContents")}}</dd>
 <dt>{{domxref("Window.find()")}}</dt>
 <dd>Recherche la chaîne de caractères donnée dans une fenêtre.</dd>
 <dt>{{domxref("Window.focus()")}}</dt>
 <dd>Donne la focalisation à la fenêtre en cours.</dd>
 <dt>{{domxref("Window.forward()")}} {{Non-standard_inline}} {{obsolete_inline}}</dt>
 <dd>Avance la fenêtre d'un document dans l'historique.</dd>
 <dt>{{domxref("Window.getAttention()")}} {{Non-standard_inline}} {{obsolete_inline}}</dt>
 <dd>Fait flasher l'icône de l'application.</dd>
 <dt>{{domxref("Window.getAttentionWithCycleCount()")}}</dt>
 <dd>{{todo("NeedsContents")}}</dd>
 <dt>{{domxref("Window.getComputedStyle()")}}</dt>
 <dd>Récupère un style calculé pour l'élément donné. Un style calculé indique les valeurs de toutes les propriétés CSS de l'élément.</dd>
 <dt>{{domxref("Window.getDefaultComputedStyle()")}} {{Non-standard_inline}}</dt>
 <dd>Récupère le style calculé par défaut pour l'élément indiqué, en ignorant les feuilles de style d'auteur.</dd>
 <dt>{{domxref("Window.getSelection()")}}</dt>
 <dd>Renvoie l'objet de sélection représentant les éléments sélectionnés.</dd>
 <dt>{{domxref("Window.home()")}} {{Non-standard_inline}} {{obsolete_inline}}</dt>
 <dd>Renvoie le navigateur à la page d'accueil.</dd>
 <dt>{{domxref("Window.matchMedia()")}} {{gecko_minversion_inline("6.0")}}</dt>
 <dd>Renvoie un objet {{domxref("MediaQueryList")}} représentant la chaîne d'interrogation de média spécifiée.</dd>
 <dt>{{domxref("Window.maximize()")}}</dt>
 <dd>{{todo("NeedsContents")}}</dd>
 <dt>{{domxref("Window.minimize()")}} (top-level XUL windows only)</dt>
 <dd>Minimize la fenêtre.</dd>
 <dt>{{domxref("Window.moveBy()")}}</dt>
 <dd>Déplace la fenêtre en cours de la quantité indiquée.</dd>
 <dt>{{domxref("Window.moveTo()")}}</dt>
 <dd>Déplace la fenêtre vers les coordonnées spécifiées.</dd>
 <dt>{{domxref("Window.open()")}}</dt>
 <dd>Ouvre une nouvelle fenêtre.</dd>
 <dt>{{domxref("Window.openDialog()")}} {{Non-standard_inline}} {{obsolete_inline}}</dt>
 <dd>Ouvre une nouvelle fenêtre de dialogue.</dd>
 <dt>{{domxref("Window.postMessage()")}}</dt>
 <dd>Fournit un moyen sécurisé pour une fenêtre d'envoyer une chaîne de données à une autre fenêtre, qui n'a pas besoin d'être dans le même domaine que la première.</dd>
 <dt>{{domxref("Window.prompt()")}}</dt>
 <dd>Ouvre la boîte de dialogue d'impression du document en cours.</dd>
 <dt>{{domxref("Window.prompt()")}}</dt>
 <dd>Renvoie le texte saisi par l'utilisateur dans une boîte de dialogue à invite.</dd>
 <dt>{{domxref("Window.releaseEvents()")}} {{Non-standard_inline}} {{Deprecated_inline}}</dt>
 <dd>Annule la capture des évènements d'un certain type par la fenêtre.</dd>
 <dt>{{domxref("Window.requestAnimationFrame()")}} {{gecko_minversion_inline("2.0")}}</dt>
 <dd>Indique au navigateur qu'une animation est en cours, en demandant au navigateur de planifier une redessinage de la fenêtre lors de l'image d'animation suivante.</dd>
 <dt>{{domxref("Window.requestIdleCallback()")}}  {{experimental_inline}}</dt>
 <dd>Active la planification de tâches pendant les périodes d'inactivité du navigateur.</dd>
 <dt>{{domxref("Window.resizeBy()")}}</dt>
 <dd>Redimensionne la fenêtre en cours d'une certaine quantité.</dd>
 <dt>{{domxref("Window.resizeTo()")}}</dt>
 <dd>Redimensionne dynamiquement la fenêtre.</dd>
 <dt>{{domxref("Window.restore()")}} {{Non-standard_inline}} {{obsolete_inline}}</dt>
 <dd>{{todo("NeedsContents")}}</dd>
 <dt>{{domxref("Window.routeEvent()")}} {{obsolete_inline(24)}}</dt>
 <dd>{{todo("NeedsContents")}}</dd>
 <dt>{{domxref("Window.scroll()")}}</dt>
 <dd>Fait défiler la fenêtre à un endroit particulier dans le document.</dd>
 <dt>{{domxref("Window.scrollBy()")}}</dt>
 <dd>Fait défiler le document dans la fenêtre de la quantité indiquée.</dd>
 <dt>{{domxref("Window.scrollByLines()")}} {{Non-standard_inline}}</dt>
 <dd>Fait défiler le document du nombre de lignes indiqué.</dd>
 <dt>{{domxref("Window.scrollByPages()")}} {{Non-standard_inline}}</dt>
 <dd>Fait défiler le document en cours du nombre de pages indiqué.</dd>
 <dt>{{domxref("Window.scrollTo()")}}</dt>
 <dd>Fait défiler à un jeu de coordonnées particulier dans le document.</dd>
 <dt>{{domxref("Window.setCursor()")}} {{Non-standard_inline}} (top-level XUL windows only)</dt>
 <dd>Change le curseur pour la fenêtre en cours.</dd>
 <dt>{{domxref("Window.setImmediate()")}}</dt>
 <dd>Exécute une fonction après que le navigateur a terminé d'autres tâches lourdes</dd>
 <dt>{{domxref("Window.setResizable()")}} {{Non-standard_inline}}</dt>
 <dd>Inverse la possibilité pour un utilisateur de redimensionner une fenêtre.</dd>
 <dt>{{domxref("Window.sizeToContent()")}} {{Non-standard_inline}}</dt>
 <dd>Dimensionne la fenêtre en fonction de son contenu.</dd>
 <dt>{{domxref("Window.stop()")}}</dt>
 <dd>Cette méthode arrête le chargement de la fenêtre.</dd>
 <dt>{{domxref("Window.updateCommands()")}} {{Non-standard_inline}}</dt>
 <dd>Met à jour l'état des commandes de la fenêtre chrome en cours (IU).</dd>
</dl>

<h3 id="Méthodes_implémentées_depuis_ailleurs">Méthodes implémentées depuis ailleurs</h3>

<dl>
 <dt>{{domxref("EventTarget.addEventListener()")}}</dt>
 <dd>Enregistre un gestionnaire d'événement pour un type d'événement spécifique dans la fenêtre.</dd>
 <dt>{{domxref("WindowOrWorkerGlobalScope.atob()")}}</dt>
 <dd>Décode une chaîne de données qui a été codée en utilisant l'encodage en base 64.</dd>
 <dt>{{domxref("WindowOrWorkerGlobalScope.btoa()")}}</dt>
 <dd>Crée une chaîne ASCII codée en base 64 à partir d'une chaîne de données binaires.</dd>
 <dt>{{domxref("WindowOrWorkerGlobalScope.clearInterval()")}}</dt>
 <dd>Annule l'exécution répétée définie en utilisant {{domxref("WindowOrWorkerGlobalScope.setInterval ()")}}.</dd>
 <dt>{{domxref("WindowOrWorkerGlobalScope.clearTimeout()")}}</dt>
 <dd>Annule l'exécution différée définie en utilisant {{domxref("WindowOrWorkerGlobalScope.setTimeout ()")}}.</dd>
 <dt>{{domxref("WindowOrWorkerGlobalScope.createImageBitmap()")}}</dt>
 <dd>Accepte une variété de sources d'images différentes, et renvoie un {{domxref("Promise")}} qui se résout en une {{domxref("ImageBitmap")}}. En option, la source est détourée avec le rectangle des pixels d'origine en (sx, sy) et de largeur sw, et de hauteur sh.</dd>
 <dt>{{domxref("WindowOrWorkerGlobalScope.fetch()")}}</dt>
 <dd>Démarre le processus de récupération d'une ressource à partir du réseau.</dd>
 <dt>{{domxref("EventTarget.removeEventListener")}}</dt>
 <dd>Supprime un gestionnaire d'événement de la fenêtre.</dd>
 <dt>{{domxref("WindowOrWorkerGlobalScope.setInterval()")}}</dt>
 <dd>Planifie une fonction à exécuter à chaque fois qu'un nombre donné de millisecondes s'est écoulé.</dd>
 <dt>{{domxref("WindowOrWorkerGlobalScope.setTimeout()")}}</dt>
 <dd>Planifie une fonction à exécuter dans un laps de temps donné.</dd>
</dl>

<h3 id="Méthodes_obsolètes">Méthodes obsolètes</h3>

<dl>
 <dt>{{domxref("Window.showModalDialog()")}} {{obsolete_inline}}</dt>
 <dd>Affiche un dialogue modal. <strong>Cette méthode a été complètement supprimée dans Chrome 43, et dans Firefox 55</strong>.</dd>
</dl>

<h2 id=".C3.89v.C3.A8nements">Gestionnaires d'évènements</h2>

<p>Ce sont des propriétés de l'objet window qui peuvent être définies pour établir des gestionnaires d'événements pour les différentes choses qui peuvent se produire dans la fenêtre et qui pourraient être intéressantes.</p>

<p><em>Cette interface hérite des gestionnaires d'événements de l'interface {{domxref("EventTarget")}} et elle implémente les gestionnaires d'événements de {{domxref("WindowEventHandlers")}}.</em></p>

<div class="note">
<p><strong>Note :</strong> à partir de {{Gecko ("9.0")}}, vous pouvez maintenant utiliser la syntaxe <code>if ("onabort" in window)</code> pour déterminer si une propriété de gestionnaire d'événements donnée existe ou non. Cela est dû au fait que les interfaces du gestionnaire d'événements ont été mises à jour pour être des interfaces Web IDL correctes. Voir les gestionnaires d'événements DOM pour plus de détails.</p>
</div>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onabort")}}</dt>
 <dt> </dt>
 <dd>Appelé quand le chargement d'une ressource a été avorté, comme par le fait qu'un utilisateur annule un chargement alors qu'il était encore en cours.</dd>
</dl>

<dl>
 <dt>{{domxref("WindowEventHandlers.onafterprint")}}</dt>
 <dd>Appelé lorsque la boîte de dialogue d'impression est fermée. Voir l'événement {{event ("afterprint")}}.</dd>
 <dt>{{domxref("WindowEventHandlers.onbeforeprint")}}</dt>
 <dd>Appelé lorsque la boîte de dialogue d'impression est ouverte. Voir l'événement {{event ("beforeprint")}}.</dd>
 <dt>{{domxref("Window.onbeforeinstallprompt")}}</dt>
 <dd>Propriété de gestionnaire d'événements qui est déclenchée avant qu'un utilisateur ne soit invité à enregistrer un site Web sur un écran d'accueil sur mobile.</dd>
 <dt>{{domxref("WindowEventHandlers.onbeforeunload")}}</dt>
 <dd>Propriété de gestionnaire d'événements pour les événements avant-déchargement dans la fenêtre.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onblur")}}</dt>
 <dd>Appelé après que la fenêtre a perdu la focalisation, comme en raison d'une fenêtre contextuelle.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onchange")}}</dt>
 <dd>Propriété de gestionnaire d'événements pour les événements de changement dans la fenêtre.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onclick")}}</dt>
 <dd>Appelé après qu'un QUELCONQUE bouton de la souris est pressé &amp; relâché.</dd>
</dl>

<dl>
 <dt>{domxref("GlobalEventHandlers.ondblclick")}}</dt>
 <dd>Appelé quand un double clic est fait avec un QUELCONQUE bouton de la souris.</dd>
 <dt>{{domxref("GlobalEventHandlers.onclose")}}</dt>
 <dd>Appelé après la fermeture de la fenêtre.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.oncontextmenu")}}</dt>
 <dd>Appelé lorsque le bouton DROIT de la souris est enfoncé.</dd>
</dl>

<dl>
 <dt>{{domxref("Window.ondevicelight")}}</dt>
 <dd>Propriété de gestionnaire d'événements pour tous les changements de niveaux de luminosité ambiante.</dd>
 <dt>{{domxref("Window.ondevicemotion")}} {{gecko_minversion_inline("6.0")}}</dt>
 <dd>Appelé si l'accéléromètre détecte un changement (pour les appareils mobiles).</dd>
 <dt>{{domxref("Window.ondeviceorientation")}} {{gecko_minversion_inline("6.0")}}</dt>
 <dd>Appelé lorsque l'orientation est modifiée (pour les appareils mobiles).</dd>
 <dt>{{domxref("Window.ondeviceorientationabsolute")}} {{non-standard_inline}} Chrome only</dt>
 <dd>Propriété de gestionnaire d'événements pour tout changement d'orientation de l'appareil.</dd>
 <dt>{{domxref("Window.ondeviceproximity")}}</dt>
 <dd>Propriété de gestionnaire d'événement pour l'événement de proximité de l'appareil.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onerror")}}</dt>
 <dd>Appelé lorsqu'une ressource ne se charge pas OU lorsqu'une erreur se produit lors de l'exécution. Voir l'événement {{event("error")}}.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onfocus")}}</dt>
 <dd>Appelé après que la fenêtre a reçu ou récupéré la focalisation. Voir les événements {{event("focus")}}.</dd>
</dl>

<dl>
 <dt>{{domxref("WindowEventHandlers.onhashchange")}} {{gecko_minversion_inline("1.9.2")}}</dt>
 <dd>Propriété de gestionnaire d'événements pour les événements {{event('hashchange')}} dans la fenêtre ; appelé lorsque la partie de l'URL après la marque hash ("#") change.</dd>
 <dt>{{domxref("Window.onappinstalled")}}</dt>
 <dd>Appelé lorsque la page est installée en tant que webapp. Voir l'événement {{event('appinstalled')}}.</dd>
 <dt>{{domxref("Window.ongamepadconnected")}}</dt>
 <dd>Représente un gestionnaire d'événements qui sera exécuté lorsqu'une manette de jeu est branchée (lorsque l'événement {{event('gamepadconnected')}} se déclenche).</dd>
 <dt>{{domxref("Window.ongamepaddisconnected")}}</dt>
 <dd>Représente un gestionnaire d'événements qui s'exécutera quand une manette de jeu est débranchée (lorsque l'événement {{event('gamepaddisconnected')}} se déclenche).</dd>
 <dt>{{domxref("Window.oninput")}}</dt>
 <dd>Appelée lorsque la valeur d'un élément &lt;input&gt; change.</dd>
 <dt>{{domxref("GlobalEventHandlers.onkeydown")}}</dt>
 <dd>Appelé lorsque vous commencez à presser une touche QUELCONQUE. Voir l'événement {{event("keydown")}}.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onkeypress")}}</dt>
 <dd>Appelé lorsqu'une touche (à l'exception de Shift, Fn et CapsLock) est en position pressée. Voir l'événement {{event("keypress")}}.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onkeyup")}}</dt>
 <dd>Appelé lorsque vous avez fini de relâcher une touche QUELCONQUE. Voir l'événement {{event("keyup")}}.</dd>
</dl>

<dl>
 <dt>{{domxref("WindowEventHandlers.onlanguagechange")}}</dt>
 <dd>Propriété de gestionnaire d'événements pour les événements {{event("languagechange")}} dans la fenêtre.</dd>
 <dt>{{domxref("GlobalEventHandlers.onload")}}</dt>
 <dd>Appelé après que toutes les ressources et les DOM ont été entièrement chargés. NE SERA PAS appelé lorsque la page est chargée à partir du cache, comme avec le bouton arrière.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onmousedown")}}</dt>
 <dd>Appelé quand un bouton QUELCONQUE de la souris est pressé.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onmousemove")}}</dt>
 <dd>Appelé en continu quand la souris est déplacée dans la fenêtre.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onmouseout")}}</dt>
 <dd>Appelé lorsque le pointeur quitte la fenêtre.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onmouseover")}}</dt>
 <dd>Appelé lorsque le pointeur entre dans la fenêtre.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onmouseup")}}</dt>
 <dd>Appelé quand un bouton QUELCONQUE de la souris est relâché.</dd>
</dl>

<dl>
 <dt>{{domxref("Window.onmozbeforepaint")}} {{gecko_minversion_inline("2.0")}}</dt>
 <dd>Propriété de gestionnaire d'événements pour l'événement MozBeforePaint, qui est déclenché avant de repeindre la fenêtre si l'événement a été demandé par un appel à la méthode {{domxref("Window.mozRequestAnimationFrame()")}}.</dd>
 <dt>{{domxref("WindowEventHandlers.onoffline")}}</dt>
 <dd>Appelé lorsque la connexion réseau est perdue. Voir l'événement {{event("offline")}}.</dd>
 <dt>{{domxref("WindowEventHandlers.ononline")}}</dt>
 <dd>Appelé lorsque la connexion réseau est établie. Voir l'événement {{event("online")}}.</dd>
 <dt>{{domxref("WindowEventHandlers.onpagehide")}}</dt>
 <dd>Appelé lorsque l'utilisateur quitte la page, avant l'événement onunload. Voir l'événement {{event("pagehide")}}.</dd>
 <dt>{{domxref("WindowEventHandlers.onpageshow")}}</dt>
 <dd>Appelé après toutes les ressources et les DOM ont été entièrement chargés. Voir l'événement {{event("pageshow")}}.</dd>
 <dt>{{domxref("Window.onpaint")}}</dt>
 <dd>Propriété de gestionnaire d'évènement pour les évènements de dessin de la fenêtre.</dd>
</dl>

<dl>
 <dt>{{domxref("WindowEventHandlers.onpopstate")}} {{gecko_minversion_inline("2.0")}}</dt>
 <dd>Appelé quand le bouton arrière est pressé.</dd>
 <dt>{{domxref("Window.onrejectionhandled")}} {{experimental_inline}}</dt>
 <dd>Gestionnaire d'événements pour les événements de rejet {{jsxref("Promise")}} gérés.</dd>
 <dt>{{domxref("GlobalEventHandlers.onreset")}}</dt>
 <dd>Appelé lorsqu'un formulaire est réinitialisé</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onresize")}}</dt>
 <dd>Appelé en continu lorsque vous redimensionnez la fenêtre.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onscroll")}}</dt>
 <dd>Appelé lorsque la barre de défilement est déplacée par un moyen QUELCONQUE. Si la ressource correspond entièrement à la fenêtre, cet événement ne peut pas être invoqué.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onwheel")}}</dt>
 <dd>Appelé lorsque la roue de la souris est tournée autour d'un axe quelconque.</dd>
 <dt>{{domxref("GlobalEventHandlers.onselect")}}</dt>
 <dd>Appelé après le texte dans un champ de saisie est sélectionné.</dd>
</dl>

<dl>
 <dt>{{domxref("GlobalEventHandlers.onselectionchange")}}</dt>
 <dd>Est un {{event("Event_handlers", "event handler")}} représentant le code à appeler lorsque l'événement {{event("selectionchange")}} est déclenché.</dd>
 <dt>{{domxref("WindowEventHandlers.onstorage")}}</dt>
 <dd>Appelé en cas de changement dans le stockage de session ou le stockage local. Voir l'événement {{event("storage")}}.</dd>
 <dt>{{domxref("GlobalEventHandlers.onsubmit")}}</dt>
 <dd>Appelé lorsqu'un formulaire est soumis.</dd>
</dl>

<dl>
 <dt>{{domxref("WindowEventHandlers.onunhandledrejection")}} {{experimental_inline}}</dt>
 <dd>Gestionnaire d'événements pour les événements de rejet {{jsxref("Promise")}} non gérés.</dd>
 <dt>{{domxref("WindowEventHandlers.onunload")}}</dt>
 <dd>Appelé lorsque l'utilisateur quitte la page.</dd>
</dl>

<dl>
 <dt>{{domxref("Window.onuserproximity")}}</dt>
 <dd>Propriété de gestionnaire d'événements pour les événements de proximité d'utilisateur.</dd>
 <dt>{{domxref("Window.onvrdisplayconnect")}}</dt>
 <dd>Représente un gestionnaire d'événements qui s'exécutera lorsqu'un périphérique RV compatible a été connecté à l'ordinateur (lorsque l'événement {{event("vrdisplayconnected")}} se déclenche).</dd>
 <dt>{{domxref("Window.onvrdisplaydisconnect")}}</dt>
 <dd>Représente un gestionnaire d'événements qui s'exécutera lorsqu'un périphérique RV compatible a été déconnecté de l'ordinateur (lorsque l'événement {{event("vrdisplaydisconnected")}} se déclenche).</dd>
 <dt>{{domxref("Window.onvrdisplayactivate")}}</dt>
 <dd>Représente un gestionnaire d'événements qui s'exécutera lorsqu'un affichage peut être présenté (lorsque l'événement {{event("vrdisplayactivate")}} se déclenche), par exemple si un HMD a été déplacé pour sortir de veille, ou a été réveillé en le mettant sur soi.</dd>
 <dt>{{domxref("Window.onvrdisplaydeactivate")}}</dt>
 <dd>Représente un gestionnaire d'événements qui s'exécute lorsqu'un affichage ne peut plus être présenté (lorsque l'événement {{event ("vrdisplaydeactivate")}} se déclenche), par exemple si un HMD est passé en veille ou en hibernation en raison d'une période d'inactivité.</dd>
 <dt>{{domxref("Window.onvrdisplayblur")}}</dt>
 <dd>Représente un gestionnaire d'événements qui s'exécutera lorsque la présentation sur un affichage a été suspendue pour une raison quelconque par le navigateur, le SE ou le matériel de RV (lorsque l'événement {{event("vrdisplayblur")}} se déclenche - par exemple, lorsque l'utilisateur interagit avec un menu système ou un navigateur, pour empêcher le suivi ou la perte d'expérience.</dd>
 <dt>{{domxref("Window.onvrdisplayfocus")}}</dt>
 <dd>Représente un gestionnaire d'événements qui sera exécuté lorsque la présentation sur un afficheur a repris après avoir perdu la focalisation (lorsque l'événement {{event("vrdisplayfocus")}} se déclenche).</dd>
 <dt>{{domxref("Window.onvrdisplaypresentchange")}}</dt>
 <dd>Représente un gestionnaire d'événements qui s'exécute lorsque l'état de présentation d'un périphérique de RV change, c'est-à-dire qu'il passe de présentation à non présentation, ou vice versa (lorsque l'événement {{event("vrdisplaypresentchange")}} se déclenche).</dd>
</dl>

<h2 id="Constructeurs">Constructeurs</h2>

<p>Voir aussi les <a href="/fr-FR/docs/DOM/DOM_Reference">Interfaces DOM</a>.</p>

<dl>
 <dt>{{domxref("DOMParser")}}</dt>
 <dd><code>DOMParser</code> peut analyser un source XML ou HTML stocké dans une chaîne de caractères en un <a href="/fr-FR/docs/DOM/document">Document</a> DOM. <code>DOMParser</code> est spécifié dans <a href="https://w3c.github.io/DOM-Parsing/">DOM Parsing et Serialization</a>.</dd>
 <dt>{{domxref("Window.GeckoActiveXObject")}}</dt>
 <dd>{{todo("NeedsContents")}}</dd>
 <dt>{{domxref("Image")}}</dt>
 <dd>Used for creating an {{domxref("HTMLImageElement")}}.</dd>
 <dt>{{domxref("Option")}}</dt>
 <dd>Used for creating an {{domxref("HTMLOptionElement")}}</dd>
 <dt>{{domxref("Window.QueryInterface")}}</dt>
 <dd>{{todo("NeedsContents")}}</dd>
 <dt>{{domxref("Window.XMLSerializer")}}</dt>
 <dd>{{todo("NeedsContents")}}</dd>
 <dt>{{domxref("Worker")}}</dt>
 <dd>Used for creating a <a href="/en-US/docs/DOM/Using_web_workers">Web worker</a></dd>
 <dt>{{domxref("Window.XPCNativeWrapper")}}</dt>
 <dd>{{todo("NeedsContents")}}</dd>
 <dt>{{domxref("Window.XPCSafeJSObjectWrapper")}}</dt>
 <dd>{{todo("NeedsContents")}}</dd>
</dl>

<h2 id="Interfaces">Interfaces</h2>

<p>Voir <a href="/fr/docs/Web/API/Document_Object_Model">Référence du DOM</a></p>

<h2 id="Voir_aussi">Voir aussi</h2>

<ul>
 <li><a href="/fr/docs/Mozilla/Working_with_windows_in_chrome_code">Travailler avec des fenêtres dans le code chrome</a></li>
</ul>