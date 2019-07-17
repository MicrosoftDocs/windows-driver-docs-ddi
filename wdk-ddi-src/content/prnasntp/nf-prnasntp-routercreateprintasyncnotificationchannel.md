---
UID: NF:prnasntp.RouterCreatePrintAsyncNotificationChannel
title: RouterCreatePrintAsyncNotificationChannel function (prnasntp.h)
description: The RouterCreatePrintAsyncNotificationChannel function creates an asynchronous notification channel that is associated with a printer or print server.
old-location: print\routercreateprintasyncnotificationchannel.htm
tech.root: print
ms.assetid: 11f9a438-861f-42ef-b4f5-f64b0b9d658a
ms.date: 04/20/2018
ms.keywords: RouterCreatePrintAsyncNotificationChannel, RouterCreatePrintAsyncNotificationChannel , RouterCreatePrintAsyncNotificationChannel function [Print Devices], print.routercreateprintasyncnotificationchannel, prnasntp/RouterCreatePrintAsyncNotificationChannel, spoolfnc_24cb45ed-2f72-4a13-9a40-c1197c41aae7.xml
ms.topic: function
f1_keywords:
 - "prnasntp/RouterCreatePrintAsyncNotificationChannel"
req.header: prnasntp.h
req.include-header: Prnasntp.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Spoolss.dll
api_name:
- RouterCreatePrintAsyncNotificationChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# RouterCreatePrintAsyncNotificationChannel function


## -description


The <code>RouterCreatePrintAsyncNotificationChannel</code> function creates an asynchronous notification channel that is associated with a printer or print server.


## -parameters




### -param pName [in]

A pointer to a null-terminated string that specifies the name of the printer or print server.


### -param pNotificationType [in]

A pointer to a GUID that represents the type of notifications sent through this channel.


### -param eNotifyFilter




### -param eConversationStyle [in]

The type of communication: unidirectional or bidirectional.


### -param pCallback [in]

A pointer to the callback function that is called to deliver the response notifications, when bidirectional communication is in effect. This parameter is ignored when unidirectional communication is in effect.


### -param ppIAsynchNotification






#### - eNotificationFilter [in]

A filter for the session or user that receives the notifications.


#### - ppIAsyncNotification [out]

A pointer to a variable that receives the address of the interface object that represents the notification channel.


## -returns



<code>RouterCreatePrintAsyncNotificationChannel</code> returns S_OK on success and returns a standard COM error code otherwise.




## -remarks



In some cases, you must release the channel that you created with the <code>RouterCreatePrintAsyncNotificationChannel</code> function by calling <b>Release</b> on IPrintAsyncNotifyChannel. For information about when to release a channel, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/notification-channel">Notification Channel</a>.



