---
title: OnPlayerCommandText
description: Callback ini terpanggil ketika player memasukan command dengan garis miring.
tags: ["player"]
---

## Deskripsi

Callback ini akan terpanggil ketika player memasukan command kedalam chat. Command atau perintah apapun yang dimulai dengan garis miring. contohnya seperti /help

| Nama      | Deskripsi                                                             |
| --------- | --------------------------------------------------------              |
| playerid  | ID Dari pemain yang memasukkan command atau perintah.                 |
| cmdtext[] | Perintah yang dimasukan kedalam chat dengan garis miring              |

## Returns

Callback Ini akan selalu dipanggil paling pertama dalam filterscripts, jadi mengganti dengan return 1 adalah cara untuk memblokir script lain untuk melihatnya atau mengaksesnya terlebih dahulu.

## Contoh

```c
public OnPlayerCommandText(playerid, cmdtext[])
{
    if(!strcmp(cmdtext, "/help", true))
    {
        SendClientMessage(playerid, -1, "SERVER: Ini adalah command /help");
        return 1;
        // return 1 akan memberitahukan kepada server bahwa command atau perintah berhasil diproses.
        // OnPlayerCommandText jadi tidak akan terpanggil lagi di script lain.
    }
    return 0;
    // Mengganti dengan return 0 akan memberitahukan kepada server bahwa perintah atau command belum diproses oleh script ini.
    // OnPlayerCommandText akan terpanggil di script lain sampai salah satunya mengganti ke return 1.
    // Jika tidak ada script yang memulai dengan return 1, maka pesan yang akan muncul kepada player adalah 'SERVER: Unknown Command'.
}
```

## Catatan

:::tip

Callback ini akan terpanggil juga oleh NPC.

:::

## Related Functions

- [SendRconCommand](../functions/SendRconCommand.md): Mengirimkan perintah atau command RCON melalui script.
