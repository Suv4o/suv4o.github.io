# suv4o.github.io

Hosts the public key for **charge-line**, a personal proof of concept that sends planned EV trips to
the owner's own Tesla via Tesla's Fleet API.

- `/.well-known/appspecific/com.tesla.3p.public-key.pem`: the app's P-256 **public** key. Tesla
  fetches it when the app is registered and when an owner pairs the app's key, so it must stay
  hosted here. The private key is **not** in this repo.
- `/callback/`: fallback OAuth redirect that displays the authorisation code. Only needed if Tesla
  won't accept an `http://localhost` redirect URI.
- `/privacy.html`, `/terms.html`: policy pages for the Tesla developer application.
- `.nojekyll`: stops GitHub Pages' Jekyll build from skipping the `.well-known` folder.

Don't add a custom domain. GitHub Pages would then redirect `suv4o.github.io` to it, and the key
must be served without a redirect.
