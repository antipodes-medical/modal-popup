# Modal Popup

## Installation

```shell
yarn add @antipodes-medical/modal-popup
```

Dans le Javascript :

```javascript
import '@antipodes-medical/modal-popup'
```

## Utilisation

```html

<modal-popup id="my-modal">
    <h2 id="dialog-title">Ma fenêtre modale</h2>
    <p id="dialog-desc">Je suis une fenêtre modale accessible.</p>
    <form action="" method="post">
        <p>
            <label for="email">Email</label>
            <br />
            <input type="email" id="email" />
        </p>
        <p>
            <label for="password">Mot de passe</label>
            <br />
            <input type="password" id="password" />
        </p>
        <p>
            <button type="submit">Valider</button>
        </p>
    </form>
</modal-popup>

<button type="button" data-modal-popup="my-modal">
    Ouvrir ma fenêtre modale
</button>
<a href="#" data-modal-popup="my-modal">
    Ouvrir ma fenêtre modale
</a>
```

Lors du clic sur un élément avec l'attribut `data-modal-popup="my-modal"`, la popup avec l'id `my-modal` va s'ouvrir.

## Attributs disponibles

### Can't close

La popup ne sera pas fermable.

```html

<modal-popup id="my-modal" cant-close></modal-popup>
```

### No close button

La popup n'aura pas de bouton de fermeture.

```html

<modal-popup id="my-modal" no-close-button></modal-popup>
```

### Active

La popup sera active par défaut.

```html

<modal-popup id="my-modal" active></modal-popup>
```

## Évènements disponibles

### modal-popup:open

Lorsque la popup est ouverte.

```javascript
const $modal = document.getElementById('my-modal');
$modal.addEventListener('modal-popup:open', () => console.log('#my-modal popup has been opened.'));
```

### modal-popup:close

Lorsque la popup est fermée.

```javascript
const $modal = document.getElementById('my-modal');
$modal.addEventListener('modal-popup:close', () => console.log('#my-modal popup has been closed.'));
```

## Styles

Vous pouvez customiser le style des modals, voici une idée de ce que vous pouvez-faire :

```scss
modal-popup {
    position: fixed;
    width: 100vw;
    z-index: 100;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    display: flex;
    padding: 2.4rem;
    overflow-y: scroll;
    -webkit-overflow-scrolling: touch;
    background-color: rgba(0, 0, 0, .75);
    pointer-events: none;
    opacity: 0;
    transition: opacity .2s;
}
modal-popup.is-active {
    pointer-events: auto;
    opacity: 1;
}
modal-popup > div {
    flex: 1;
    max-width: 48rem;
    margin: auto;
    padding: 2.4rem;
    background-color: #FFF;
}
```