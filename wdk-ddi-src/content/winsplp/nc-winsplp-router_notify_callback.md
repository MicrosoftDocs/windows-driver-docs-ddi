---
UID: NC:winsplp.ROUTER_NOTIFY_CALLBACK
title: ROUTER_NOTIFY_CALLBACK
author: windows-driver-content
description: "."
old-location: print\router_notify_callback.htm
old-project: print
ms.assetid: 97D8FEEA-B6D7-4AD7-A067-B503AF8F23FF
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.router_notify_callback, ROUTER_NOTIFY_CALLBACK callback function [Print Devices], ROUTER_NOTIFY_CALLBACK, ROUTER_NOTIFY_CALLBACK, ROUTER_NOTIFY_CALLBACK, winsplp/ROUTER_NOTIFY_CALLBACK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Winsplp.h
apiname:
-	ROUTER_NOTIFY_CALLBACK
product: Windows
targetos: Windows
req.typenames: SCARD_IO_REQUEST, *PSCARD_IO_REQUEST, *LPSCARD_IO_REQUEST
req.product: Windows 10 or later.
---

# ROUTER_NOTIFY_CALLBACK callback


## -description





## -prototype


````
ROUTER_NOTIFY_CALLBACK ROUTER_NOTIFY_CALLBACK;

 ROUTER_NOTIFY_CALLBACK(
  _In_  DWORD                    dwCommand,
  _In_  PVOID                    pContext,
  _In_  DWORD                    dwColor,
  _In_  PPRINTER_NOTIFY_INFO     pNofityInfo,
  _In_  DWORD                    fdwFlags,
  _Out_ PDWORD                   pdwResult
)
{ ... }
````


## -parameters




#### - dwCommand [in]



#### - pContext [in]



#### - dwColor [in]



#### - pNofityInfo [in]



#### - fdwFlags [in]



#### - pdwResult [out]


