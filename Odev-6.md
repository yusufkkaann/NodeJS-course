const Koa = require("koa");
const app = new Koa();

// Middleware - "/hakkimizda" sayfası için
app.use(async (ctx, next) => {
  if (ctx.path === "/hakkimizda") {
    ctx.body = "<h1>Hakkımızda sayfası burada!</h1>";
  } else {
    await next();
  }
});
app.use(async (ctx, next) => {
  if (ctx.path === "/iletisim") {
    ctx.body = "<h1>İletişim sayfası burada!</h1>";
  } else {
    await next();
  }
});
app.use(async (ctx, next) => {
  if (ctx.path === "/") {
    ctx.body = "<h1>Ana sayfa burada!</h1>";
  } else {
    await next();
  }
});

app.use(async (ctx) => {
  ctx.status = 404; // 404 durum kodunu ayarla
  ctx.body = "<h1>Sayfa bulunamadı!</h1>"; // 404 sayfasını göster
});

// Sunucuyu dinlemek için
app.listen(3000, () => {
  console.log("Sunucu çalışıyor...");
});
