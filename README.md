[![LaravelTest](https://github.com/Trane54/CuentaTest/actions/workflows/laravel.yml/badge.svg)](https://github.com/Trane54/CuentaTest/actions/workflows/laravel.yml)

# 💸 Projecte `CuentaTest` amb TDD (Laravel)

Aquest projecte implementa una classe `Cuenta` que simula el comportament d’un compte bancari. El desenvolupament s’ha realitzat seguint la metodologia **TDD (Test Driven Development)** amb Laravel i PHPUnit.

## 🧪 Objectiu del projecte

Validar el funcionament de la classe `Cuenta` mitjançant proves unitàries que asseguren el comportament correcte en diversos escenaris com ara ingressos, retirades i transferències.

---

## ⚙️ Funcionalitats

### 🟢 Creació d’un compte corrent

- Els comptes es creen amb saldo **zero** per defecte.

### ➕ Ingressos

- Afegixen la quantitat especificada al saldo.
- No hi ha comissions.
- **No** s’admeten ingressos negatius.
- Els ingressos han de tenir **com a màxim 2 decimals**.
- La quantitat **màxima** que es pot ingressar és de **6000€**.

#### Exemples:

- ✅ Ingressar 100 ➝ saldo = 100  
- ❌ Ingressar -100 ➝ saldo = 0  
- ❌ Ingressar 100.457 ➝ saldo = 0  
- ❌ Ingressar 6000.01 ➝ saldo = 0  

### ➖ Retirades

- Resta la quantitat del saldo.
- **No** es pot retirar més del que hi ha disponible.
- **No** es poden retirar quantitats negatives.
- Les retirades tenen també **2 decimals màxim**.
- El límit de retirada és de **6000€** per operació.

#### Exemples:

- ✅ Retirar 100 amb saldo 500 ➝ saldo = 400  
- ❌ Retirar 100 amb saldo 50 ➝ saldo = 50 (no canvia)  
- ❌ Retirar -100 ➝ saldo no canvia  
- ❌ Retirar 100.457 ➝ saldo no canvia  
- ❌ Retirar 6000.01 ➝ saldo no canvia  

### 🔁 Transferències

- Permet transferir diners d’un compte a un altre.
- **No** es poden transferir quantitats negatives.
- Es manté un **límit diari de 3000€** en transferències per compte.

#### Exemples:

- ✅ Transferir 100 d’un compte amb 500 a un amb 50 ➝ saldo = 400 i 150  
- ❌ Transferir -100 ➝ saldos no canvien  
- ❌ Transferir 3000.01 ➝ saldos no canvien  
- ✅ Transferir 2000 i després 1200 ➝ només la segona es bloqueja si supera el límit de 3000€/dia

---

## 🧪 Tests

Aquest projecte incorpora proves unitàries mitjançant `php artisan test`, cobrin tots els casos descrits anteriorment.

Per executar els tests:

```bash
php artisan test
```

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT). 
