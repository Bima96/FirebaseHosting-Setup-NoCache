# FirebaseHosting-Setup-NoCache

Steps Before Deploy: 
1. after setup firebase init:
2. copy file firebase.json (FirebaseHosting-Setup-NoCache/firebase.json)
   or copy and paste the code below into your file firebase.json
{
  "hosting": {
    "public": "public",
    "headers": [
      {
        "source": "/**",
        "headers": [
          {
            "key": "Cache-Control",
            "value": "no-cache, no-store, must-revalidate"
          }
        ]
      },
      {
        "source":
          "**/*.@(jpg|jpeg|gif|png|svg|webp|js|css|eot|otf|ttf|ttc|woff|woff2|font.css)",
        "headers": [
          {
            "key": "Cache-Control",
            "value": "max-age=0, s-maxage=604800"
          }
        ]
      }
    ],
    "ignore": ["firebase.json", "**/.*", "**/node_modules/**"]
  }
}

3. After that you can deploy on firebase hosting
4. happy realtimes change!
