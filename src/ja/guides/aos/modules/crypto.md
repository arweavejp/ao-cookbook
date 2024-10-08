# crypto

## 概要

`crypto` モジュールは、純粋な Lua で実装されたハッシュ、暗号化、復号化などの暗号化プリミティブのセットを提供します。データをハッシュ、暗号化、復号化するためのいくつかの機能を提供し、安全な通信とデータストレージの開発を簡素化します。このドキュメントでは、モジュールの機能、インストール、および使用方法について説明します。

<!-- # crypto

## Overview

The `crypto` module provides a set of cryptographic primitives like digests, ciphers and other cryptographic algorithms in pure Lua. It offers several functionalities to hash, encrypt and decrypt data, simplifying the development of secure communication and data storage. This document will guide you through the module's functionalities, installation, and usage.
-->

## Usage

```lua
local crypto = require(".crypto");
```

## プリミティブ

1. ダイジェスト (sha1, sha2, sha3, keccak, blake2b など)
2. サイファー (AES, ISSAC, Morus, NORX など)
3. ランダム数生成器 (ISAAC)
4. MAC (HMAC)
5. KDF (PBKDF2)
6. ユーティリティ (Array, Stream, Queue など)

---

# ダイジェスト

## MD2

与えられたメッセージの MD2 ダイジェストを計算します。

- **パラメータ:**

  - `stream` (Stream): ストリーム形式のメッセージ

- **戻り値:** 異なる形式でダイジェストを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式のダイジェスト。
  - `asHex()`: 16進形式の文字列としてのダイジェスト。
  - `asString()`: 文字列形式のダイジェスト。

<!--
## Primitives

1. Digests (sha1, sha2, sha3, keccak, blake2b, etc.)
2. Ciphers (AES, ISSAC, Morus, NORX, etc.)
3. Random Number Generators (ISAAC)
4. MACs (HMAC)
5. KDFs (PBKDF2)
6. Utilities (Array, Stream, Queue, etc.)

---

# Digests

## MD2

Calculates the MD2 digest of a given message.

- **Parameters:**

  - `stream` (Stream): The message in form of stream

- **Returns:** A table containing functions to get digest in different formats.
  - `asBytes()`: The digest as byte table.
  - `asHex()`: The digest as string in hexadecimal format.
  - `asString()`: The digest as string format.
-->

Example:

```lua
local str = crypto.utils.stream.fromString("ao")

return crypto.digest.md2(str).asHex() -- 0d4e80edd07bee6c7965b21b25a9b1ea
```

## MD4

与えられたメッセージの MD4 ダイジェストを計算します。

- **パラメータ:**

  - `stream` (Stream): ストリーム形式のメッセージ

- **戻り値:** 異なる形式でダイジェストを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式のダイジェスト。
  - `asHex()`: 16進形式の文字列としてのダイジェスト。
  - `asString()`: 文字列形式のダイジェスト。

<!--
Calculates the MD4 digest of a given message.

- **Parameters:**

  - `stream` (Stream): The message in form of stream

- **Returns:** A table containing functions to get digest in different formats.
  - `asBytes()`: The digest as byte table.
  - `asHex()`: The digest as string in hexadecimal format.
  - `asString()`: The digest as string format.
-->

Example:

```lua
local str = crypto.utils.stream.fromString("ao")

return crypto.digest.md4(str).asHex() -- e068dfe3d8cb95311b58be566db66954
```

## MD5

与えられたメッセージの MD5 ダイジェストを計算します。

- **パラメータ:**

  - `stream` (Stream): ストリーム形式のメッセージ

- **戻り値:** 異なる形式でダイジェストを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式のダイジェスト。
  - `asHex()`: 16進形式の文字列としてのダイジェスト。
  - `asString()`: 文字列形式のダイジェスト。

<!-- ## MD5

Calculates the MD5 digest of a given message.

- **Parameters:**

  - `stream` (Stream): The message in form of stream

- **Returns:** A table containing functions to get digest in different formats.
  - `asBytes()`: The digest as byte table.
  - `asHex()`: The digest as string in hexadecimal format.
  - `asString()`: The digest as string format.
-->

Example:

```lua
local str = crypto.utils.stream.fromString("ao")

return crypto.digest.md5(str).asHex() -- adac5e63f80f8629e9573527b25891d3
```

## SHA1

与えられたメッセージの SHA1 ダイジェストを計算します。

- **パラメータ:**

  - `stream` (Stream): ストリーム形式のメッセージ

- **戻り値:** 異なる形式でダイジェストを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式のダイジェスト。
  - `asHex()`: 16進形式の文字列としてのダイジェスト。
  - `asString()`: 文字列形式のダイジェスト。

<!-- ## SHA1

Calculates the SHA1 digest of a given message.

- **Parameters:**

  - `stream` (Stream): The message in form of stream

- **Returns:** A table containing functions to get digest in different formats.
  - `asBytes()`: The digest as byte table.
  - `asHex()`: The digest as string in hexadecimal format.
  - `asString()`: The digest as string format.
-->

Example:

```lua
local str = crypto.utils.stream.fromString("ao")

return crypto.digest.sha1(str).asHex() -- c29dd6c83b67a1d6d3b28588a1f068b68689aa1d
```

## SHA2_256

与えられたメッセージの SHA2-256 ダイジェストを計算します。

- **パラメータ:**
  - `stream` (Stream): ストリーム形式のメッセージ
- **戻り値:** 異なる形式でダイジェストを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式のダイジェスト。
  - `asHex()`: 16進形式の文字列としてのダイジェスト。
  - `asString()`: 文字列形式のダイジェスト。

<!-- ## SHA2_256

Calculates the SHA2-256 digest of a given message.

- **Parameters:**
  - `stream` (Stream): The message in form of stream
- **Returns:** A table containing functions to get digest in different formats.
  - `asBytes()`: The digest as byte table.
  - `asHex()`: The digest as string in hexadecimal format.
  - `asString()`: The digest as string format.
-->

Example:

```lua
local str = crypto.utils.stream.fromString("ao")

return crypto.digest.sha2_256(str).asHex() -- ba7816bf8f01cfea414140de5dae2223b00361a396177a9cb410ff61f20015ad
```

## SHA2_512

与えられたメッセージの SHA2-512 ダイジェストを計算します。

- **パラメータ:**
  - `msg` (string): ダイジェストを計算するメッセージ
- **戻り値:** 異なる形式でダイジェストを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式のダイジェスト。
  - `asHex()`: 16進形式の文字列としてのダイジェスト。
  - `asString()`: 文字列形式のダイジェスト。

Example:

```lua
local str = "ao"

return crypto.digest.sha2_512(str).asHex() -- 6f36a696b17ce5a71efa700e8a7e47994f3e134a5e5f387b3e7c2c912abe94f94ee823f9b9dcae59af99e2e34c8b4fb0bd592260c6720ee49e5deaac2065c4b1
```

## SHA3

以下の関数が含まれています。

1. `sha3_256`
2. `sha3_512`
3. `keccak256`
4. `keccak512`

各関数は、与えられたメッセージのそれぞれのダイジェストを計算します。

- **パラメータ:**

  - `msg` (string): ダイジェストを計算するメッセージ

- **戻り値:** 異なる形式でダイジェストを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式のダイジェスト。
  - `asHex()`: 16進形式の文字列としてのダイジェスト。
  - `asString()`: 文字列形式のダイジェスト。

<!--
## SHA3

It contains the following functions:

1. `sha3_256`
2. `sha3_512`
3. `keccak256`
4. `keccak512`

Each function calculates the respective digest of a given message.

- **Parameters:**

  - `msg` (string): The message to calculate the digest

- **Returns:** A table containing functions to get digest in different formats.
  - `asBytes()`: The digest as byte table.
  - `asHex()`: The digest as string in hexadecimal format.
  - `asString()`: The digest as string format. -->

Example:

```lua

local str = "ao"

crypto.digest.sha3_256(str).asHex()  -- 1bbe785577db997a394d5b4555eec9159cb51f235aec07514872d2d436c6e985
crypto.digest.sha3_512(str).asHex()  -- 0c29f053400cb1764ce2ec555f598f497e6fcd1d304ce0125faa03bb724f63f213538f41103072ff62ddee701b52c73e621ed4d2254a3e5e9a803d83435b704d
crypto.digest.keccak256(str).asHex() -- 76da52eec05b749b99d6e62bb52333c1569fe75284e6c82f3de12a4618be00d6
crypto.digest.keccak512(str).asHex() -- 046fbfad009a12cef9ff00c2aac361d004347b2991c1fa80fba5582251b8e0be8def0283f45f020d4b04ff03ead9f6e7c43cc3920810c05b33b4873b99affdea

```

## Blake2b

与えられたメッセージのBlake2bダイジェストを計算します。

- **パラメータ:**

  - `data` (string): ハッシュ化するデータ。
  - `outlen` (number): 出力ハッシュの長さ（オプション） **デフォルトは64**。
  - `key` (string): ハッシュ化に使用するキー（オプション） **デフォルトは""**。

- **戻り値:** 異なる形式でダイジェストを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式のダイジェスト。
  - `asHex()`: 16進形式の文字列としてのダイジェスト。
  - `asString()`: 文字列形式のダイジェスト。

<!--
## Blake2b

Calculates the Blake2b digest of a given message.

- **Parameters:**

  - `data` (string): The data to be hashed.
  - `outlen` (number): The length of the output hash (optional) **default is 64**.
  - `key` (string): The key to be used for hashing (optional) **default is ""**.

- **Returns:** A table containing functions to get digest in different formats.
  - `asBytes()`: The digest as byte table.
  - `asHex()`: The digest as string in hexadecimal format.
  - `asString()`: The digest as string format. -->

Example:

```lua
local str = "ao"

crypto.digest.blake2b(str).asHex() -- 576701fd79a126f2c414ef94adf1117c88943700f312679d018c29c378b2c807a3412b4e8d51e191c48fb5f5f54bf1bca29a714dda166797b3baf9ead862ae1d
crypto.digest.blake2b(str, 32).asHex() -- 7050811afc947ba7190bb3c0a7b79b4fba304a0de61d529c8a35bdcbbb5544f4
crypto.digest.blake2b(str, 32, "secret_key").asHex() -- 203c101980fdf6cf24d78879f2e3db86d73d91f7d60960b642022cd6f87408f8
```

---

# Ciphers

## AES

高度暗号化標準（AES）は、機密情報を暗号化するために使用される対称ブロック暗号です。暗号化と復号化の2つの機能があります。

### Encrypt

AESアルゴリズムを使用して、与えられたメッセージを暗号化します。

- **パラメータ:**

  - `data` (string): 暗号化するデータ。
  - `key` (string): 暗号化に使用するキー。
  - `iv` (string) オプション: 暗号化に使用する初期化ベクトル。 **デフォルトは""**
  - `mode` (string) オプション: 暗号化に使用する操作モード。 **デフォルトは"CBC"**。 使用可能なモードは `CBC`, `ECB`, `CFB`, `OFB`, `CTR` です。
  - `keyLength` (number) オプション: 暗号化に使用するキーの長さ。 **デフォルトは128**。

- **戻り値:** 異なる形式で暗号化されたデータを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式の暗号化データ。
  - `asHex()`: 16進形式の文字列としての暗号化データ。
  - `asString()`: 文字列形式の暗号化データ。

## Decrypt

AESアルゴリズムを使用して、与えられたメッセージを復号化します。

- **パラメータ:**

  - `cipher` (string): ヘックスエンコードされた暗号化データ。
  - `key` (string): 復号化に使用するキー。
  - `iv` (string) オプション: 復号化に使用する初期化ベクトル。 **デフォルトは""**
  - `mode` (string) オプション: 復号化に使用する操作モード。 **デフォルトは"CBC"**。 使用可能なモードは `CBC`, `ECB`, `CFB`, `OFB`, `CTR` です。
  - `keyLength` (number) オプション: 復号化に使用するキーの長さ。 **デフォルトは128**。

- **戻り値:** 異なる形式で復号化されたデータを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式の復号化データ。
  - `asHex()`: 16進形式の文字列としての復号化データ。
  - `asString()`: 文字列形式の復号化データ。

<!--
# Ciphers

## AES

The Advanced Encryption Standard (AES) is a symmetric block cipher used to encrypt sensitive information. It has two functions encrypt and decrypt.

### Encrypt

Encrypts a given message using the AES algorithm.

- **Parameters:**

  - `data` (string): The data to be encrypted.
  - `key` (string): The key to be used for encryption.
  - `iv` (string) optional: The initialization vector to be used for encryption. **default is ""**
  - `mode` (string) optional: The mode of operation to be used for encryption. **default is "CBC"**. Available modes are `CBC`, `ECB`, `CFB`, `OFB`, `CTR`.
  - `keyLength` (number) optional: The length of the key to use for encryption. **default is 128**.

- **Returns:** A table containing functions to get encrypted data in different formats.
  - `asBytes()`: The encrypted data as byte table.
  - `asHex()`: The encrypted data as string in hexadecimal format.
  - `asString()`: The encrypted data as string format.

## Decrypt

Decrypts a given message using the AES algorithm.

- **Parameters:**

  - `cipher` (string): Hex Encoded encrypted data.
  - `key` (string): The key to be used for decryption.
  - `iv` (string) optional: The initialization vector to be used for decryption. **default is ""**
  - `mode` (string) optional: The mode of operation to be used for decryption. **default is "CBC"**. Available modes are `CBC`, `ECB`, `CFB`, `OFB`, `CTR`.
  - `keyLength` (number) optional: The length of the key to use for decryption. **default is 128**.

- **Returns:** A table containing functions to get decrypted data in different formats.
  - `asBytes()`: The decrypted data as byte table.
  - `asHex()`: The decrypted data as string in hexadecimal format.
  - `asString()`: The decrypted data as string format. -->

Example:

```lua
local str = "ao"

local iv = "super_secret_shh"
local key_128 = "super_secret_shh"

local encrypted = crypto.cipher.aes.encrypt("ao", key, iv).asHex() -- A3B9E6E1FBD9D46930E5F76807C84B8E
local decrypted = crypto.cipher.aes.decrypt(encrypted, key, iv).asHex() -- 616F0000000000000000000000000000

crypto.utils.hex.hexToString(decrypted) -- ao

```

## ISSAC Cipher

ISAACは、暗号的に安全な擬似乱数生成器（CSPRNG）であり、ストリーム暗号です。以下の機能があります。

1. `seedIsaac`: 指定されたシードでISAAC暗号をシードします。
2. `getRandomChar`: ISAAC暗号を使用してランダムな文字を生成します。
3. `random`: ISAAC暗号を使用して指定された範囲内のランダムな数値を生成します。
4. `getRandom`: ISAAC暗号を使用してランダムな数値を生成します。
5. `encrypt`: ISAAC暗号を使用して与えられたメッセージを暗号化します。
6. `decrypt`: ISAAC暗号を使用して与えられたメッセージを復号化します。

### Encrypt

ISAAC暗号を使用して、与えられたメッセージを暗号化します。

- **パラメータ:**
  - `msg` (string): 暗号化するメッセージ。
  - `key` (string): 暗号化に使用するキー。
- **戻り値:** 異なる形式で暗号化されたデータを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式の暗号化データ。
  - `asHex()`: 16進形式の文字列としての暗号化データ。
  - `asString()`: 文字列形式の暗号化データ。

### Decrypt

ISAAC暗号を使用して、与えられたメッセージを復号化します。

- **パラメータ:**
  - `cipher` (string): ヘックスエンコードされた暗号化データ。
  - `key` (string): 復号化に使用するキー。
- **戻り値:** 異なる形式で復号化されたデータを取得するための関数を含むテーブル。
  - `asBytes()`: バイトテーブル形式の復号化データ。
  - `asHex()`: 16進形式の文字列としての復号化データ。
  - `asString()`: 文字列形式の復号化データ。

<!--
## ISSAC Cipher

ISAAC is a cryptographically secure pseudo-random number generator (CSPRNG) and stream cipher. It has the following functions

1. `seedIsaac`: Seeds the ISAAC cipher with a given seed.
2. `getRandomChar`: Generates a random character using the ISAAC cipher.
3. `random`: Generates a random number between a given range using the ISAAC cipher.
4. `getRandom`: Generates a random number using the ISAAC cipher.
5. `encrypt`: Encrypts a given message using the ISAAC cipher.
6. `decrypt`: Decrypts a given message using the ISAAC cipher.

### Encrypt

Encrypts a given message using the ISAAC cipher.

- **Parameters:**
  - `msg` (string): The message to be encrypted.
  - `key` (string): The key to be used for encryption.
- **Returns:** A table containing functions to get encrypted data in different formats.
  - `asBytes()`: The encrypted data as byte table.
  - `asHex()`: The encrypted data as string in hexadecimal format.
  - `asString()`: The encrypted data as string format.

### Decrypt

Decrypts a given message using the ISAAC cipher.

- **Parameters:**
  - `cipher` (string): Hex Encoded encrypted data.
  - `key` (string): Key to be used for decryption.
- **Returns:** A table containing functions to get decrypted data in different formats.
  - `asBytes()`: The decrypted data as byte table.
  - `asHex()`: The decrypted data as string in hexadecimal format.
  - `asString()`: The decrypted data as string format. -->

Example:

```lua
local message = "ao";
local key = "secret_key";

local encrypted = crypto.cipher.issac.encrypt(message, key)
local decrypted = crypto.cipher.issac.decrypt(encrypted.asString(), key) -- ao


encrypted.asHex() -- 7851
```

### random

ISAAC暗号を使用して、ランダムな数値を生成します。

- **パラメータ:**
  - `min` (number) optional: ランダム数値の最小値。**デフォルトは0**。
  - `max` (number) optional: ランダム数値の最大値。**デフォルトは2^31 - 1**。
  - `seed` (string) optional: ランダム数値を生成するために使用されるシード。**デフォルトはmath.random(0,2^32 - 1)**。
- **戻り値:** 指定された範囲内のランダムな数値。

<!--
### random

Generates a random number using the ISAAC cipher.

- **Parameters:**
  - `min` (number) optional: The minimum value of the random number. **defaults to 0**.
  - `max` (number) optional: The maximum value of the random number. **defaults to 2^31 - 1**.
  - `seed` (string) optional: The seed to be used for generating the random number. **defaults to math.random(0,2^32 - 1)**.
- **Returns:** A random number between the given range.
-->

Example:

```lua
crypto.cipher.issac.random(0, 100) -- 42
```

<!--
## Morus Cipher

MORUS is a high-performance authenticated encryption algorithm submitted to the CAESAR competition, and recently selected as a finalist.

### Encrypt

Encrypts a given message using the MORUS cipher.

- **Parameters:**
  - `key` (string): The encryption key (16 or 32-byte string).
  - `iv` (string): The nonce or initial value (16-byte string).
  - `msg` (string): The message to encrypt (variable length string).
  - `ad` (string) optional: The additional data (variable length string). **defaults to ""**.
- **Returns:** A table containing functions to get encrypted data in different formats.
  - `asBytes()`: The encrypted data as byte table.
  - `asHex()`: The encrypted data as string in hexadecimal format.
  - `asString()`: The encrypted data as string format.

### Decrypt

Decrypts a given message using the MORUS cipher.

- **Parameters:**
  - `key` (string): The encryption key (16 or 32-byte string).
  - `iv` (string): The nonce or initial value (16-byte string).
  - `cipher` (string): The encrypted message (variable length string).
  - `adLen` (number) optional: The length of the additional data (variable length string). **defaults to 0**.
- **Returns:** A table containing functions to get decrypted data in different formats.
  - `asBytes()`: The decrypted data as byte table.
  - `asHex()`: The decrypted data as string in hexadecimal format.
  - `asString()`: The decrypted data as string format.
-->

## Morus Cipher

MORUSは、高性能の認証暗号化アルゴリズムで、CAESARコンペティションに提出され、最近ファイナリストとして選ばれました。

### Encrypt

与えられたメッセージをMORUS暗号を使用して暗号化します。

- **パラメータ:**
  - `key` (string): 暗号化キー（16または32バイトの文字列）。
  - `iv` (string): ノンスまたは初期値（16バイトの文字列）。
  - `msg` (string): 暗号化するメッセージ（可変長の文字列）。
  - `ad` (string) optional: 追加データ（可変長の文字列）。**デフォルトは""**。
- **戻り値:** 異なる形式で暗号化されたデータを取得するための関数を含むテーブル。
  - `asBytes()`: 暗号化されたデータをバイトテーブルとして取得。
  - `asHex()`: 暗号化されたデータを16進形式の文字列として取得。
  - `asString()`: 暗号化されたデータを文字列形式で取得。

### Decrypt

与えられたメッセージをMORUS暗号を使用して復号化します。

- **パラメータ:**
  - `key` (string): 暗号化キー（16または32バイトの文字列）。
  - `iv` (string): ノンスまたは初期値（16バイトの文字列）。
  - `cipher` (string): 暗号化されたメッセージ（可変長の文字列）。
  - `adLen` (number) optional: 追加データの長さ（可変長の文字列）。**デフォルトは0**。
- **戻り値:** 異なる形式で復号化されたデータを取得するための関数を含むテーブル。
  - `asBytes()`: 復号化されたデータをバイトテーブルとして取得。
  - `asHex()`: 復号化されたデータを16進形式の文字列として取得。
  - `asString()`: 復号化されたデータを文字列形式で取得。

Example:

```lua
local m = "ao"
local k = "super_secret_shh"
local iv = "0000000000000000"
local ad= ""

local e = crypto.cipher.morus.encrypt(k, iv, m, ad)
local d = crypto.cipher.morus.decrypt(k, iv, e.asString(), #ad) -- ao

e.asHex() -- 514ed31473d8fb0b76c6cbb17af35ed01d0a
```

<!--
## NORX Cipher

NORX is an authenticated encryption scheme with associated data that was selected, along with 14 other primitives, for the third phase of the ongoing CAESAR competition. It is based on the sponge construction and relies on a simple permutation that allows efficient and versatile implementations.

### Encrypt

Encrypts a given message using the NORX cipher.

- **Parameters:**
  - `key` (string): The encryption key (32-byte string).
  - `nonce` (string): The nonce or initial value (32-byte string).
  - `plain` (string): The message to encrypt (variable length string).
  - `header` (string) optional: The additional data (variable length string). **defaults to ""**.
  - `trailer` (string) optional: The additional data (variable length string). **defaults to ""**.
- **Returns:** A table containing functions to get encrypted data in different formats.
  - `asBytes()`: The encrypted data as byte table.
  - `asHex()`: The encrypted data as string in hexadecimal format.
  - `asString()`: The encrypted data as string format.

### Decrypt

Decrypts a given message using the NORX cipher.

- **Parameters:**
  - `key` (string): The encryption key (32-byte string).
  - `nonce` (string): The nonce or initial value (32-byte string).
  - `crypted` (string): The encrypted message (variable length string).
  - `header` (string) optional: The additional data (variable length string). **defaults to ""**.
  - `trailer` (string) optional: The additional data (variable length string). **defaults to ""**.
- **Returns:** A table containing functions to get decrypted data in different formats.
  - `asBytes()`: The decrypted data as byte table.
  - `asHex()`: The decrypted data as string in hexadecimal format.
  - `asString()`: The decrypted data as string format.
-->

## NORX Cipher

NORXは、関連データ付きの認証暗号化スキームで、現在進行中のCAESARコンペティションの第3フェーズにおいて、他の14のプリミティブと共に選ばれました。これは、スポンジ構造に基づいており、効率的で多用途な実装を可能にするシンプルな置換に依存しています。

### Encrypt

与えられたメッセージをNORX暗号を使用して暗号化します。

- **パラメータ:**
  - `key` (string): 暗号化キー（32バイトの文字列）。
  - `nonce` (string): ノンスまたは初期値（32バイトの文字列）。
  - `plain` (string): 暗号化するメッセージ（可変長の文字列）。
  - `header` (string) optional: 追加データ（可変長の文字列）。**デフォルトは""**。
  - `trailer` (string) optional: 追加データ（可変長の文字列）。**デフォルトは""**。
- **戻り値:** 異なる形式で暗号化されたデータを取得するための関数を含むテーブル。
  - `asBytes()`: 暗号化されたデータをバイトテーブルとして取得。
  - `asHex()`: 暗号化されたデータを16進形式の文字列として取得。
  - `asString()`: 暗号化されたデータを文字列形式で取得。

### Decrypt

与えられたメッセージをNORX暗号を使用して復号化します。

- **パラメータ:**
  - `key` (string): 暗号化キー（32バイトの文字列）。
  - `nonce` (string): ノンスまたは初期値（32バイトの文字列）。
  - `crypted` (string): 暗号化されたメッセージ（可変長の文字列）。
  - `header` (string) optional: 追加データ（可変長の文字列）。**デフォルトは""**。
  - `trailer` (string) optional: 追加データ（可変長の文字列）。**デフォルトは""**。
- **戻り値:** 異なる形式で復号化されたデータを取得するための関数を含むテーブル。
  - `asBytes()`: 復号化されたデータをバイトテーブルとして取得。
  - `asHex()`: 復号化されたデータを16進形式の文字列として取得。
  - `asString()`: 復号化されたデータを文字列形式で取得。

Example:

```lua
local key = "super_duper_secret_password_shhh"
local nonce = "00000000000000000000000000000000"

local data = "ao"

-- Header and trailer are optional
local header, trailer = data, data

local encrypted = crypto.cipher.norx.encrypt(key, nonce, data, header, trailer).asString()
local decrypted = crypto.cipher.norx.decrypt(key, nonce, encrypted, header, trailer) -- ao

local authTag = encrypted:sub(#encrypted-32+1)

crypto.utils.hex.stringToHex(encrypted) -- 0bb35a06938e6541eccd4440adb7b46118535f60b09b4adf378807a53df19fc4ea28
crypto.utils.hex.stringToHex(authTag) -- 5a06938e6541eccd4440adb7b46118535f60b09b4adf378807a53df19fc4ea28
```

---

# Random Number Generators

The module contains a random number generator using ISAAC which is a cryptographically secure pseudo-random number generator (CSPRNG) and stream cipher.

- **Parameters:**
  - `min` (number) optional: The minimum value of the random number. **defaults to 0**.
  - `max` (number) optional: The maximum value of the random number. **defaults to 2^31 - 1**.
  - `seed` (string) optional: The seed to be used for generating the random number. **defaults to math.random(0,2^32 - 1)**.
- **Returns:** A random number between the given range.

<!--
# Random Number Generators

The module contains a random number generator using ISAAC which is a cryptographically secure pseudo-random number generator (CSPRNG) and stream cipher.

- **Parameters:**
  - `min` (number) optional: The minimum value of the random number. **defaults to 0**.
  - `max` (number) optional: The maximum value of the random number. **defaults to 2^31 - 1**.
  - `seed` (string) optional: The seed to be used for generating the random number. **defaults to math.random(0,2^32 - 1)**.
- **Returns:** A random number between the given range.
-->

Example:

```lua
crypto.random.(0, 100, "seed") -- 42
```

---

# MACs

## HMAC

ハッシュベースのメッセージ認証コード（HMAC）は、暗号学的ハッシュ関数を使用したメッセージ認証のメカニズムです。HMACは、秘密の共有キーと組み合わせて、MD5やSHA-1などの任意の反復暗号ハッシュ関数とともに使用できます。

このモジュールは、HMACインスタンスを作成するために使用される`createHmac`という関数を公開しています。

- **パラメータ:**
  - `data` (Stream): ハッシュ化されるデータ。
  - `key` (Array): ハッシュ化に使用されるキー。
  - `algorithm` (string) optional: ハッシュ化に使用されるアルゴリズム。**デフォルトは"sha256"**。利用可能なアルゴリズムは"sha1"、"sha256"です。**デフォルトは"sha1"**。
- **戻り値:** 異なる形式でHMACを取得するための関数を含むテーブル。
  - `asBytes()`: HMACをバイトテーブルとして取得します。
  - `asHex()`: HMACを16進数形式の文字列として取得します。
  - `asString()`: HMACを文字列形式として取得します。

<!--
# MACs

## HMAC

The Hash-based Message Authentication Code (HMAC) is a mechanism for message authentication using cryptographic hash functions. HMAC can be used with any iterative cryptographic hash function, e.g., MD5, SHA-1, in combination with a secret shared key.

The modules exposes a function called `createHmac` which is used to create a HMAC instance.

- **Parameters:**
  - `data` (Stream): The data to be hashed.
  - `key` (Array): The key to be used for hashing.
  - `algorithm` (string) optional: The algorithm to be used for hashing. **default is "sha256"**. Available algorithms are "sha1", "sha256". **default is "sha1"**.
- **Returns:** A table containing functions to get HMAC in different formats.
  - `asBytes()`: The HMAC as byte table.
  - `asHex()`: The HMAC as string in hexadecimal format.
  - `asString()`: The HMAC as string format.
  -->

Example:

```lua
local data = crypto.utils.stream.fromString("ao")
local key = crypto.utils.array.fromString("super_secret_key")

crypto.mac.createHmac(data, key).asHex() -- 3966f45acb53f7a1a493bae15afecb1a204fa32d
crypto.mac.createHmac(data, key, "sha256").asHex() -- 542da02a324155d688c7689669ff94c6a5f906892aa8eccd7284f210ac66e2a7
```

---

# KDFs

## PBKDF2

パスワードベースのキー導出関数2（PBKDF2）は、ハッシュベースのメッセージ認証コード（HMAC）などの疑似乱数関数を入力パスワードまたはパスフレーズに適用し、ソルト値とともに多くの回数繰り返すことで、派生キーを生成します。この派生キーは、後続の操作で暗号化キーとして使用できます。

- **パラメータ:**
  - `password` (Array): キーを導出するためのパスワード。
  - `salt` (Array): 使用するソルト。
  - `iterations` (number): 実行する繰り返し回数。
  - `keyLen` (number): 導出するキーの長さ。
  - `digest` (string) optional: 使用するダイジェストアルゴリズム。**デフォルトは"sha1"**。利用可能なアルゴリズムは"sha1"、"sha256"です。
- **戻り値:** 異なる形式で導出されたキーを取得するための関数を含むテーブル。
  - `asBytes()`: 導出されたキーをバイトテーブルとして取得します。
  - `asHex()`: 導出されたキーを16進数形式の文字列として取得します。
  - `asString()`: 導出されたキーを文字列形式として取得します。

<!--
# KDFs

## PBKDF2

The Password-Based Key Derivation Function 2 (PBKDF2) applies a pseudorandom function, such as hash-based message authentication code (HMAC), to the input password or passphrase along with a salt value and repeats the process many times to produce a derived key, which can then be used as a cryptographic key in subsequent operations.

- **Parameters:**
  - `password` (Array): The password to derive the key from.
  - `salt` (Array): The salt to use.
  - `iterations` (number): The number of iterations to perform.
  - `keyLen` (number): The length of the key to derive.
  - `digest` (string) optional: The digest algorithm to use. **default is "sha1"**. Available algorithms are "sha1", "sha256".
- **Returns:** A table containing functions to get derived key in different formats.
  - `asBytes()`: The derived key as byte table.
  - `asHex()`: The derived key as string in hexadecimal format.
  - `asString()`: The derived key as string format.
-->

Example:

```lua
local salt = crypto.utils.array.fromString("salt")
local password = crypto.utils.array.fromString("password")
local iterations = 4
local keyLen = 16

local res = crypto.kdf.pbkdf2(password, salt, iterations, keyLen).asHex() -- C4C21BF2BBF61541408EC2A49C89B9C6
```

---

# ユーティリティ

## 配列

<!-- # Utilities

## Array -->

Example Usage:

```lua

local arr = crypto.utils.array

arr.fromString("ao") -- Array
arr.toString(arr.fromString("ao")) -- ao

arr.fromHex("616f") -- Array
arr.toHex(arr.fromHex("616f")) -- 616f

arr.concat(arr.fromString("a"), arr.fromString("o")) -- Array
arr.truncate(arr.fromString("ao"), 1) -- Array

arr.XOR(arr.fromString("a"), arr.fromString("o")) -- Array

arr.substitute(arr.fromString("a"), arr.fromString("o")) -- Array
arr.permute(arr.fromString("a"), arr.fromString("o")) -- Array

arr.copy(arr.fromString("ao")) -- Array
arr.slice(arr.fromString("ao"), 0, 1) -- Array
```

<!--
### `size`

Returns the size of the array.

- **Parameters:**
  - `arr` (Array): The array to get the size of.
- **Returns:** The size of the array.

### `fromString`

Creates an array from a string.

- **Parameters:**
  - `str` (string): The string to create the array from.
- **Returns:** The array created from the string.

### `toString`

Converts an array to a string.

- **Parameters:**
  - `arr` (Array): The array to convert to a string.
- **Returns:** The array as a string.

### `fromStream`

Creates an array from a stream.

- **Parameters:**
  - `stream` (Stream): The stream to create the array from.
- **Returns:** The array created from the stream.

### `readFromQueue`

Reads data from a queue and stores it in the array.

- **Parameters:**
  - `queue` (Queue): The queue to read data from.
  - `size` (number): The size of the data to read.
- **Returns:** The array containing the data read from the queue.

### `writeToQueue`

Writes data from the array to a queue.

- **Parameters:**
  - `queue` (Queue): The queue to write data to.
  - `array` (Array): The array to write data from.
- **Returns:** None

### `toStream`

Converts an array to a stream.

- **Parameters:**
  - `arr` (Array): The array to convert to a stream.
- **Returns:** (Stream) The array as a stream.

### `fromHex`

Creates an array from a hexadecimal string.

- **Parameters:**
  - `hex` (string): The hexadecimal string to create the array from.
- **Returns:** The array created from the hexadecimal string.

### `toHex`

Converts an array to a hexadecimal string.

- **Parameters:**
  - `arr` (Array): The array to convert to a hexadecimal string.
- **Returns:** The array as a hexadecimal string.

### `concat`

Concatenates two arrays.

- **Parameters:**
  - `a` (Array): The array to concatenate with.
  - `b` (Array): The array to concatenate.
- **Returns:** The concatenated array.

### `truncate`

Truncates an array to a given length.

- **Parameters:**
  - `a` (Array): The array to truncate.
  - `newSize` (number): The new size of the array.
- **Returns:** The truncated array.

### `XOR`

Performs a bitwise XOR operation on two arrays.

- **Parameters:**
  - `a` (Array): The first array.
  - `b` (Array): The second array.
- **Returns:** The result of the XOR operation.

### `substitute`

Creates a new array with keys of first array and values of second

- **Parameters:**
  - `input` (Array): The array to substitute.
  - `sbox` (Array): The array to substitute with.
- **Returns:** The substituted array.

### `permute`

Creates a new array with keys of second array and values of first array.

- **Parameters:**
  - `input` (Array): The array to permute.
  - `pbox` (Array): The array to permute with.
- **Returns:** The permuted array.

### `copy`

Creates a copy of an array.

- **Parameters:**
  - `input` (Array): The array to copy.
- **Returns:** The copied array.

### `slice`

Creates a slice of an array.

- **Parameters:**
  - `input` (Array): The array to slice.
  - `start` (number): The start index of the slice.
  - `stop` (number): The end index of the slice.
- **Returns:** The sliced array.

---

## Stream

Stream is a data structure that represents a sequence of bytes. It is used to store and manipulate data in a streaming fashion.
-->

### `size`

配列のサイズを返します。

- **パラメーター:**
  - `arr` (Array): サイズを取得する配列。
- **戻り値:** 配列のサイズ。

### `fromString`

文字列から配列を作成します。

- **パラメーター:**
  - `str` (string): 配列を作成するための文字列。
- **戻り値:** 文字列から作成された配列。

### `toString`

配列を文字列に変換します。

- **パラメーター:**
  - `arr` (Array): 文字列に変換する配列。
- **戻り値:** 配列を文字列として返します。

### `fromStream`

ストリームから配列を作成します。

- **パラメーター:**
  - `stream` (Stream): 配列を作成するためのストリーム。
- **戻り値:** ストリームから作成された配列。

### `readFromQueue`

キューからデータを読み取り、配列に格納します。

- **パラメーター:**
  - `queue` (Queue): データを読み取るキュー。
  - `size` (number): 読み取るデータのサイズ。
- **戻り値:** キューから読み取ったデータを含む配列。

### `writeToQueue`

配列からキューにデータを書き込みます。

- **パラメーター:**
  - `queue` (Queue): データを書き込むキュー。
  - `array` (Array): データを読み取る配列。
- **戻り値:** なし

### `toStream`

配列をストリームに変換します。

- **パラメーター:**
  - `arr` (Array): ストリームに変換する配列。
- **戻り値:** 配列をストリームとして返します。

### `fromHex`

16進数文字列から配列を作成します。

- **パラメーター:**
  - `hex` (string): 配列を作成するための16進数文字列。
- **戻り値:** 16進数文字列から作成された配列。

### `toHex`

配列を16進数文字列に変換します。

- **パラメーター:**
  - `arr` (Array): 16進数文字列に変換する配列。
- **戻り値:** 配列を16進数文字列として返します。

### `concat`

2つの配列を連結します。

- **パラメーター:**
  - `a` (Array): 連結する配列。
  - `b` (Array): 連結される配列。
- **戻り値:** 連結された配列。

### `truncate`

指定された長さに配列を切り詰めます。

- **パラメーター:**
  - `a` (Array): 切り詰める配列。
  - `newSize` (number): 配列の新しいサイズ。
- **戻り値:** 切り詰められた配列。

### `XOR`

2つの配列に対してビット単位のXOR操作を実行します。

- **パラメーター:**
  - `a` (Array): 最初の配列。
  - `b` (Array): 2番目の配列。
- **戻り値:** XOR操作の結果。

### `substitute`

最初の配列のキーと2番目の配列の値を持つ新しい配列を作成します。

- **パラメーター:**
  - `input` (Array): 置き換える配列。
  - `sbox` (Array): 置き換えるための配列。
- **戻り値:** 置き換えられた配列。

### `permute`

2番目の配列のキーと最初の配列の値を持つ新しい配列を作成します。

- **パラメーター:**
  - `input` (Array): 並べ替える配列。
  - `pbox` (Array): 並べ替えるための配列。
- **戻り値:** 並べ替えられた配列。

### `copy`

配列のコピーを作成します。

- **パラメーター:**
  - `input` (Array): コピーする配列。
- **戻り値:** コピーされた配列。

### `slice`

配列のスライスを作成します。

- **パラメーター:**
  - `input` (Array): スライスする配列。
  - `start` (number): スライスの開始インデックス。
  - `stop` (number): スライスの終了インデックス。
- **戻り値:** スライスされた配列。

---

## ストリーム

ストリームはバイトのシーケンスを表すデータ構造です。データをストリーミング方式で格納および操作するために使用されます。

Example Usage:

```lua
local stream = crypto.utils.stream

local str = "ao"
local arr = {97, 111}

stream.fromString(str) -- Stream
stream.toString(stream.fromString(str)) -- ao

stream.fromArray(arr) -- Stream
stream.toArray(stream.fromArray(arr)) -- {97, 111}

stream.fromHex("616f") -- Stream
stream.toHex(stream.fromHex("616f")) -- 616f
```

<!--
### `fromString`

Creates a stream from a string.

- **Parameters:**
  - `str` (string): The string to create the stream from.
- **Returns:** The stream created from the string.

### `toString`

Converts a stream to a string.

- **Parameters:**
  - `stream` (Stream): The stream to convert to a string.
- **Returns:** The stream as a string.

### `fromArray`

Creates a stream from an array.

- **Parameters:**
  - `arr` (Array): The array to create the stream from.
- **Returns:** The stream created from the array.

### `toArray`

Converts a stream to an array.

- **Parameters:**
  - `stream` (Stream): The stream to convert to an array.
- **Returns:** The stream as an array.

### `fromHex`

Creates a stream from a hexadecimal string.

- **Parameters:**
  - `hex` (string): The hexadecimal string to create the stream from.
- **Returns:** The stream created from the hexadecimal string.

### `toHex`

Converts a stream to a hexadecimal string.

- **Parameters:**
  - `stream` (Stream): The stream to convert to a hexadecimal string.
- **Returns:** The stream as a hexadecimal string.
-->

### `fromString`

文字列からストリームを作成します。

- **パラメーター:**
  - `str` (string): ストリームを作成するための文字列。
- **戻り値:** 文字列から作成されたストリーム。

### `toString`

ストリームを文字列に変換します。

- **パラメーター:**
  - `stream` (Stream): 文字列に変換するストリーム。
- **戻り値:** ストリームを文字列として返します。

### `fromArray`

配列からストリームを作成します。

- **パラメーター:**
  - `arr` (Array): ストリームを作成するための配列。
- **戻り値:** 配列から作成されたストリーム。

### `toArray`

ストリームを配列に変換します。

- **パラメーター:**
  - `stream` (Stream): 配列に変換するストリーム。
- **戻り値:** ストリームを配列として返します。

### `fromHex`

16進数文字列からストリームを作成します。

- **パラメーター:**
  - `hex` (string): ストリームを作成するための16進数文字列。
- **戻り値:** 16進数文字列から作成されたストリーム。

### `toHex`

ストリームを16進数文字列に変換します。

- **パラメーター:**
  - `stream` (Stream): 16進数文字列に変換するストリーム。
- **戻り値:** ストリームを16進数文字列として返します。

---

## Hex

Example Usage:

```lua
local hex = crypto.utils.hex

hex.hexToString("616f") -- ao
hex.stringToHex("ao") -- 616f
```

<!--
### `hexToString`

Converts a hexadecimal string to a string.

- **Parameters:**
  - `hex` (string): The hexadecimal string to convert to a string.
- **Returns:** The hexadecimal string as a string.

### `stringToHex`

Converts a string to a hexadecimal string.

- **Parameters:**
  - `str` (string): The string to convert to a hexadecimal string.
- **Returns:** The string as a hexadecimal string.

---

## Queue

Queue is a data structure that represents a sequence of elements. It is used to store and manipulate data in a first-in, first-out (FIFO) fashion.
-->

### `hexToString`

16進数文字列を文字列に変換します。

- **パラメーター:**
  - `hex` (string): 文字列に変換するための16進数文字列。
- **戻り値:** 16進数文字列を文字列として返します。

### `stringToHex`

文字列を16進数文字列に変換します。

- **パラメーター:**
  - `str` (string): 16進数文字列に変換するための文字列。
- **戻り値:** 文字列を16進数文字列として返します。

---

## Queue

キューは、要素のシーケンスを表すデータ構造です。最初に入れたものが最初に出る（FIFO）方式でデータを保存および操作するために使用されます。

Example Usage:

```lua
local q = crypto.utils.queue()

q.push(1)
q.push(2)
q.pop() -- 1
q.size() -- 1
q.getHead() -- 2
q.getTail() -- 2
q.reset()
```

<!-- ### `push`

Pushes an element to the queue.

- **Parameters:**
  - `queue` (Queue): The queue to push the element to.
  - `element` (any): The element to push to the queue.
- **Returns:** None

### `pop`

Pops an element from the queue.

- **Parameters:**
  - `queue` (Queue): The queue to pop the element from.
  - `element` (any): The element to pop from the queue.
- **Returns:** The popped element.

### `size`

Returns the size of the queue.

- **Parameters:** None
- **Returns:** The size of the queue.

### `getHead`

Returns the head of the queue.

- **Parameters:** None
- **Returns:** The head of the queue.

### `getTail`

Returns the tail of the queue.

- **Parameters:** None
- **Returns:** The tail of the queue.

### `reset`

Resets the queue.

- **Parameters:** None

---
-->

### `push`

キューに要素を追加します。

- **パラメーター:**
  - `queue` (Queue): 要素を追加するキュー。
  - `element` (any): キューに追加する要素。
- **戻り値:** なし

### `pop`

キューから要素を取り出します。

- **パラメーター:**
  - `queue` (Queue): 要素を取り出すキュー。
  - `element` (any): キューから取り出す要素。
- **戻り値:** 取り出された要素。

### `size`

キューのサイズを返します。

- **パラメーター:** なし
- **戻り値:** キューのサイズ。

### `getHead`

キューの先頭要素を返します。

- **パラメーター:** なし
- **戻り値:** キューの先頭要素。

### `getTail`

キューの末尾要素を返します。

- **パラメーター:** なし
- **戻り値:** キューの末尾要素。

### `reset`

キューをリセットします。

- **パラメーター:** なし

---
