---
UID: NF:prnasntp.RouterGetPrintClassObject
title: RouterGetPrintClassObject function
author: windows-driver-content
description: The RouterGetPrintClassObject function enumerates the list of print providers, searching for the print provider with the specified name and interface ID.
old-location: print\routergetprintclassobject.htm
old-project: print
ms.assetid: e2df591d-59bd-4aae-ac1b-8fdf01da3ea7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RouterGetPrintClassObject, RouterGetPrintClassObject function [Print Devices], print.routergetprintclassobject, prnasntp/RouterGetPrintClassObject, spoolfnc_ffe877d1-cb3e-49f5-a5b5-5da7c5cb9148.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Spoolss.dll
api_name:
-	RouterGetPrintClassObject
product:
- Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# RouterGetPrintClassObject function


## -description


The <code>RouterGetPrintClassObject</code> function enumerates the list of print providers, searching for the print provider with the specified name and interface ID. 


## -parameters




### -param pPrinter [in]

A pointer to a null-terminated string that contains the name of the printer or print server.


### -param riid [in]

The identifier of the requested COM interface.


### -param ppv [out]

A pointer to a variable that supplies the address of the COM interface requested in the <i>iid</i> parameter.


## -returns



This function returns S_OK on success, and a standard COM error code otherwise.



