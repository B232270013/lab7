
# BUG-04: API эвдэрхий JSON-д HTTP 200 буцааж байна

Орчин: Уншлагын жагсаалт v2.0,
Node.js v26.12.0, Arch Linux, 2026-10-20

Урьдчилсан нөхцөл:
node app.js-ийг шинээр асаасан.
Сервер localhost:3000 дээр ажиллаж байна.

## Дахин гаргах алхам

1. Terminal нээнэ.
2. Дараах командыг ажиллуулна.

```bash
curl -i -X POST http://localhost:3000/api/books \
  -H "Content-Type: application/json" \
  --data-binary 'invalid json'
```

## Хүлээгдэж байсан үр дүн

Эвдэрхий JSON өгөгдөлтэй POST хүсэлтэд
HTTP 400 Bad Request буцаах ёстой.

## Бодит үр дүн

HTTP/1.1 200 OK

{"result":"OK"}

## Ноцтой байдал

Major — API буруу бүтэцтэй хүсэлтийг
амжилттай гэж хүлээн авч байна.

## Нотолгоо

[evidence/bug-04-curl.txt](../evidence/bug-04-curl.txt)

## Олдсон аялал

Saboteur Tour
