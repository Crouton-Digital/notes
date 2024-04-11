![screenshot](https://github.com/Crouton-Digital/notes/blob/main/screenshot.jpg?raw=true)

1. We can make osmosis frontend compatible with namada extension

2. Osmosis frontend connects wallets with cosmos-kit

3. The challenge is namada extension not compatible with cosmos-kit
 - signing and sending shielded transactions is combined in a single function in namada extension, but cosmos-kit requires signing and broadcasting be exposed as separate methods

4. Our solution: implement ChainProvider and cosmos-kit compatible hooks specifically for namada:

https://github.com/Crouton-Digital/march12-shielded-app/blob/929b829ff08241f6b52ffa97ed255596860912a5/namada.tsx

5. Then replace ChainProvider with namada.ChainProvider in Osmosis frontend or any other cosmos-kti app to make it work with namada:

https://github.com/Crouton-Digital/march12-shielded-app/blob/929b829ff08241f6b52ffa97ed255596860912a5/pages/_app.tsx#L73
