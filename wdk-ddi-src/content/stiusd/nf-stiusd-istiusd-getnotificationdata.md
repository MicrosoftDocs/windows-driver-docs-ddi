---
UID: NF:stiusd.IStiUSD.GetNotificationData
title: IStiUSD::GetNotificationData (stiusd.h)
description: A still image minidriver's IStiUSD::GetNotificationData method returns a description of the most recent event that occurred on a still image device.
tech.root: image
ms.date: 04/19/2022
keywords: ["IStiUSD::GetNotificationData"]
ms.keywords: GetNotificationData, GetNotificationData method [Imaging Devices], GetNotificationData method [Imaging Devices],IStiUSD interface, IStiUSD interface [Imaging Devices],GetNotificationData method, IStiUSD.GetNotificationData, IStiUSD::GetNotificationData, image.istiusd_getnotificationdata, stifnc_1641dbac-f429-4f85-9cd0-25ef82000992.xml, stiusd/IStiUSD::GetNotificationData
req.header: stiusd.h
req.include-header: Stiusd.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IStiUSD::GetNotificationData
 - stiusd/IStiUSD::GetNotificationData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - stiusd.h
api_name:
 - IStiUSD::GetNotificationData
---

## -description

A still image minidriver's **IStiUSD::GetNotificationData* method returns a description of the most recent event that occurred on a still image device.

## -parameters

### -param lpNotify

Caller-supplied pointer to an [STINOTIFY](../sti/ns-sti-_stinotify.md) structure to receive event information.

## -returns

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in *stierr.h*. If no events have occurred since the last time the method was called, the method should return STIERR_NOEVENTS.

## -remarks

Each time a device event occurs, the still image event monitor calls**IStiUSD::GetNotificationData</b> to obtain an event description. These descriptions are added to a linked list and when an application calls [IStiDevice::GetLastNotificationData](../sti/nf-sti-istidevice-getlastnotificationdata.md), the most recent addition to the list is returned.