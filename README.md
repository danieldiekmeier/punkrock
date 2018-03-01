# Punkrock

What if you could build a website in your parent's basement? What if you could punch your laptop and people could get HTML from your server? What if you could be young and have some fun?

```
import punkrock from 'punkrock'

function Home (ctx) {
  return punkrock.render('home', { name: ctx.query.name })
}

function ListBands (ctx, page = 1) {
  const bands = await getTheBandsBackTogether()
  return punkrock.render('bands', { bands })
}

const router = new punkrock.Router([{
  route: '/',
  get: Home,
}, {
  route: '/bands', '/bands/page/:page',
  get: ListBands,
  post: AddBand
}, {
  route: '/bands/:band',
  get: ShowBand,
  put: UpdateBand
}])

const app = new punkrock.Server(router)
punkrock.listen(8080)
```

## Reviews

"`punkrock.listen` is a nice pun" – @timomeh
