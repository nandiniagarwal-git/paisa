PAISA — install steps

1. Put these files in one folder and host it over HTTPS (installing needs HTTPS):
   - Netlify: go to app.netlify.com/drop and drag the folder in. Done in a minute.
   - GitHub Pages: upload the files to a repo, then Settings > Pages > deploy from main branch.
2. Open the link on your phone.
   - Android (Chrome): tap "Install app" in the Your data card, or menu > Install app.
   - iPhone (Safari): Share > Add to Home Screen.
3. It works offline after the first load. Data stays on that device only: use Export backup in the app to move it.

To test on your laptop first: in this folder run "python3 -m http.server 8000", then open http://localhost:8000
