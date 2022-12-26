# weblog.lol sourcehut builds integration

by [Gil](https://gil.omg.lol)

## Instructions

**Heads up!:** Start with an empty repository as the scripts only track files changed in a given commit. A file needs to have changes made to its contents in relation to the previous commit in order for the updated version of the file to be uploaded to your weblog.

1. Download `example.build.yml`, rename it to `.build.yml` and add it to the root of your repo.
2. Download `secretvars.sh` and keep it somewhere safe outside your repo (we are going to put secret stuff in it).
3. In `secretvars.sh` edit line 4 and replace `foobar` with the portion of your address before the `.omg.lol` part
4. In `secretvars.sh` edit line 5 and replace `insert-api-token-here` with the API key you retrieved from [your account page](https://home.omg.lol/account#api-key)
5. In `secretvars.sh` edit line 6 and replace `myweblog` with your repo name (the part after the `https://git.sr.ht/~foobar/`)
6. Navigate to the ["secrets" section of sourcehut builds](https://builds.sr.ht/secrets)
7. Select "File" under "Secret Type", type `~/.secretvars`, type `777`, and upload the edited `secretvar.sh` file. Give it a name, for your reference, and click "Add secret"
8. On the right-hand side, a new entry will appear, copy the alphanumeric identifier over the name you gave your secret on the last step.
9. Edit `.build.yml`, edit line 3 replace `YOUR_SOURCEHUT_SECRET_ID` with the identifier you copied in the last step.
10. Add your weblog posts and pages as `.md` files under a `weblog` folder and your custom `configuration.txt` and `template.html` files under a `configuration` folder.
10. Commit and push your changes to your repo and the sourcehut builds job will automatically start. You can track its progress on the URL outputted by your console after you push your changes.

## License

TL;DR: Do whatever you want with it, no attribution required (although is always apprecciated :D). You're on your own though, no warranty/support here.

The code in this repository is made available under an MIT No Attribution license. You can read it in [`LICENSE`](LICENSE).

Improvements are always welcome!

