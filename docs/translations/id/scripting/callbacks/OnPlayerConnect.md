---
title: OnPlayerConnect
description: Callback ini terpanggil ketika pemain join kedalam server.
tags: ["player"]
---

## Deskripsi

Callback ini akan terpanggil ketika pemain join kedalam server

| Nama     | Deskripsi                         |
| -------- | --------------------------------  |
| playerid | ID pemain yang connect ke server. |

## Returns

0 - Akan menutup akses filterscript menggunakan callback ini.

1 - Memberi akses ke filterscript untuk menggunakan callback ini.

Dalam filterscripts, callback ini akan selalu terpanggil untuk pertama kali.

## Contoh

```c
public OnPlayerConnect(playerid)
{
    new string[64], pName[MAX_PLAYER_NAME];
    GetPlayerName(playerid, pName, MAX_PLAYER_NAME);
    format(string, sizeof string, "%s telah join kedalam server, selamat datang!", pName);
    SendClientMessageToAll(0xFFFFFFAA, string);
    return 1;
}
```

## Catatan

:::tip

Callback ini juga bisa terpanggil untuk NPC.

:::

## Fungsi Terkait
