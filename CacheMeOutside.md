#Cache Me Outside Walkthrough
Este es un reto OSINT, nos dan esta imagen para empezar.

![Imagen inicial](Images/69d514a8a643762d5700ec6f-1777446884950.png)

En la imagen que nos dan hay un link de koomot, siguiendo el link encontramos su nombre.

![Imagen koomot](Images/2026-06-08_13-00.png)

What is the retired hacker’s full name?
Jim Lee.

En koomot encuentro un link a github.
https://github.com/jiml33t

Al ver su historial, tan solo tiene un commit el 16 de abril de 2026.

Uso Curl para ver los datos completos del commit.

curl -H "Accept: application/vnd.github+json" \
     "https://api.github.com/repos/jiml33t/jiml33t/commits"
[
  {
    "sha": "7b2c8e0a540c36f2e09da5945066020621d6a059",
    "node_id": "C_kwDOSEE4k9oAKDdiMmM4ZTBhNTQwYzM2ZjJlMDlkYTU5NDUwNjYwMjA2MjFkNmEwNTk",
    "commit": {
      "author": {
        "name": "jimleepro1-cell",
        "email": "jimleepro1@gmail.com",
        "date": "2026-04-16T07:27:19Z"
      },
      "committer": {
        "name": "GitHub",
        "email": "noreply@github.com",
        "date": "2026-04-16T07:27:19Z"
      },
      "message": "Initial commit",
      "tree": {
        "sha": "3e58d226fe6c70d1e870054269d448d915f824d1",
        "url": "https://api.github.com/repos/jiml33t/jiml33t/git/trees/3e58d226fe6c70d1e870054269d448d915f824d1"
      },
      "url": "https://api.github.com/repos/jiml33t/jiml33t/git/commits/7b2c8e0a540c36f2e09da5945066020621d6a059",
      "comment_count": 1,
      "verification": {
        "verified": true,
        "reason": "valid",
        "signature": "-----BEGIN PGP SIGNATURE-----\n\nwsFcBAABCAAQBQJp4I9XCRC1aQ7uu5UhlAAAYoIQAA7s06lY5W6lxdAlGfkcAJ58\ndPnXAU5fySCUT0r0W9MbzPDFcZ2zhCJozg+j0ElCkrEKhy7Kb1DOONX/5X0yJK3z\n5aolXLgsQkRMySnwC4uzsqlomKzr/NISzNxpvDGm7LuTKrnpu8bSf8gCrMlogP6a\nEQf+VCtGIiP1egC+RLUbOXLocdUA4F3wzeM0BHb3b2JvkP5OF+8auv8ajexFbfK/\n2WeGuoRNh6GaQ/Y/GkgR20yeJI5mtVAsNEY4nJ030wt1vzDL0bvcvtOHp6+Lumf3\neoWWjJIXmQKT3tTZQp2457kYf47Q06CRS4rVHFcTKmA5supArxewJz7o2bzF4viN\nG/vZDA5wpTLJntZHtZlhYdt4PIRRDBW1EWAa2Lih52QlO2vSBxx600tz8QgCAzie\n8zVjU9lZs6fk/mhBknBDOS35RrfPjWBdK5Phg9aFVbl30ncuVJTirsocTCeuFA1T\nZKYC2q78kmSVuHQnF7EuVSBpK/Zz5+hGf+SHiefzlQ60b3W2ztekzcDEim8kEt0C\nkPBkCdpUZPrx9biG4qODn7JW3qc/ZOSNZPzEv3v5Ufh2WFrCbDnR0NCQC/6yujEP\nZz7b4whzS3isrJTjP3XUSRWtgIN+ggam/QaiKYdlmxmWQsAn/mVUDnPozs8U8/v3\nmV9FQba2WeI5JBblpbxq\n=21Y1\n-----END PGP SIGNATURE-----\n",
        "payload": "tree 3e58d226fe6c70d1e870054269d448d915f824d1\nauthor jimleepro1-cell <jimleepro1@gmail.com> 1776324439 -0400\ncommitter GitHub <noreply@github.com> 1776324439 -0400\n\nInitial commit",
        "verified_at": "2026-04-16T07:27:20Z"
      }
    },
    "url": "https://api.github.com/repos/jiml33t/jiml33t/commits/7b2c8e0a540c36f2e09da5945066020621d6a059",
    "html_url": "https://github.com/jiml33t/jiml33t/commit/7b2c8e0a540c36f2e09da5945066020621d6a059",
    "comments_url": "https://api.github.com/repos/jiml33t/jiml33t/commits/7b2c8e0a540c36f2e09da5945066020621d6a059/comments",
    "author": {
      "login": "jiml33t",
      "id": 276522146,
      "node_id": "U_kgDOEHtkog",
      "avatar_url": "https://avatars.githubusercontent.com/u/276522146?v=4",
      "gravatar_id": "",
      "url": "https://api.github.com/users/jiml33t",
      "html_url": "https://github.com/jiml33t",
      "followers_url": "https://api.github.com/users/jiml33t/followers",
      "following_url": "https://api.github.com/users/jiml33t/following{/other_user}",
      "gists_url": "https://api.github.com/users/jiml33t/gists{/gist_id}",
      "starred_url": "https://api.github.com/users/jiml33t/starred{/owner}{/repo}",
      "subscriptions_url": "https://api.github.com/users/jiml33t/subscriptions",
      "organizations_url": "https://api.github.com/users/jiml33t/orgs",
      "repos_url": "https://api.github.com/users/jiml33t/repos",
      "events_url": "https://api.github.com/users/jiml33t/events{/privacy}",
      "received_events_url": "https://api.github.com/users/jiml33t/received_events",
      "type": "User",
      "user_view_type": "public",
      "site_admin": false
    },
    "committer": {
      "login": "web-flow",
      "id": 19864447,
      "node_id": "MDQ6VXNlcjE5ODY0NDQ3",
      "avatar_url": "https://avatars.githubusercontent.com/u/19864447?v=4",
      "gravatar_id": "",
      "url": "https://api.github.com/users/web-flow",
      "html_url": "https://github.com/web-flow",
      "followers_url": "https://api.github.com/users/web-flow/followers",
      "following_url": "https://api.github.com/users/web-flow/following{/other_user}",
      "gists_url": "https://api.github.com/users/web-flow/gists{/gist_id}",
      "starred_url": "https://api.github.com/users/web-flow/starred{/owner}{/repo}",
      "subscriptions_url": "https://api.github.com/users/web-flow/subscriptions",
      "organizations_url": "https://api.github.com/users/web-flow/orgs",
      "repos_url": "https://api.github.com/users/web-flow/repos",
      "events_url": "https://api.github.com/users/web-flow/events{/privacy}",
      "received_events_url": "https://api.github.com/users/web-flow/received_events",
      "type": "User",
      "user_view_type": "public",
      "site_admin": false
    },
    "parents": [

    ]
  }
]

En el campo email esta la segunda flag.

What email address did he accidentally expose?
"email": "jimleepro1@gmail.com"

La siguiente flag es un numero de telefono. Tan solo tengo un correo y una cuenta de koomot.
He buscado cuentas de correo o usuarios como jimleepro1, jim l33t, he usado holehe para ver servicios en los que haya usado esa cuenta, sin éxito.

He enviado un correo, y tiene una respuesta programada.

![Imagen correo](Images/2026-06-08_13-23.png)

En la imagen se puede ver su número de teléfono y una posible compañia, L33t Security.

What is his phone number?
+40 743 321 239
