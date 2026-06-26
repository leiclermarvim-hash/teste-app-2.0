const CACHE_NAME = 'gestao-pedidos-v1';
const ASSETS = [
  './!DOCTYPE1.html',
  './manifest.json',
  './icon-192.png',
  './icon-512.png'
];

// Instala o Service Worker e guarda os arquivos no cache
self.addEventListener('install', (e) => {
  e.waitUntil(
    caches.open(CACHE_NAME).then((cache) => {
      return cache.addAll(ASSETS);
    })
  );
});

// Executa as requisições usando o cache quando offline
self.addEventListener('fetch', (e) => {
  e.respondWith(
    caches.match(e.request).then((response) => {
      return response || fetch(e.request);
    })
  );
});