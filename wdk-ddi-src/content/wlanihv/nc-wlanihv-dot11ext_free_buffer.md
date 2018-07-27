---
UID: NC:wlanihv.DOT11EXT_FREE_BUFFER
title: DOT11EXT_FREE_BUFFER
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extfreebuffer.htm
tech.root: netvista
ms.assetid: a6e49914-29c0-47d2-936b-17c48958cb36
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXT_FREE_BUFFER, Dot11ExtFreeBuffer, Dot11ExtFreeBuffer callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_af721540-28a8-43c2-a649-ce0f6fb9adce.xml, netvista.dot11extfreebuffer, wlanihv/Dot11ExtFreeBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wlanihv.h
api_name:
-	Dot11ExtFreeBuffer
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_FREE_BUFFER callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtFreeBuffer</b> function to free memory allocated through a call to
  <a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>.


## -prototype


````
VOID WINAPI * Dot11ExtFreeBuffer(
  _In_opt_ LPVOID pvMemory
);
````


## -parameters




### -param pvMemory [in, optional]

A pointer to the buffer to be freed. If the value of
     <i>pvMemory</i> is <b>NULL</b>, the
     <b>Dot11ExtFreeBuffer</b> function returns immediately.


## -returns



None




## -remarks



The IHV Extension DLL must not call the
    <b>Dot11ExtFreeBuffer</b> function for any variable-length buffer allocated
    within an IHV handler function and passed to the operating system through a parameter to the function. In
    this situation, the operating system is responsible for freeing the buffer after the return of the IHV
    Handler function.

For more information about the IHV Handler functions, see
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
    Functions</a>.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>



 

 


