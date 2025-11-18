立ち上げ手順

clone後にディレクトリ移動し下記を実行してください

```
docker run --rm -v $(pwd):/app -w /app composer install
```

```
sail up -d
```

```
cp .env.example .env
```

```
sail npm run dev
```
```
sail artisan migrate
```

```
sail artisan db:seed
```

ログインする前に下記を行う（１，２どれか）

１phpmyadminにてfactor関連のデータを消す

２下記ファイルでコメントアウトを行う

fortify.php
```
    'features' => [
        Features::registration(),
        Features::resetPasswords(),
        Features::emailVerification(),
        // Features::twoFactorAuthentication([
            // 'confirm' => true,
            // 'confirmPassword' => true,
            // // 'window' => 0
        ///]),
    ],
```


