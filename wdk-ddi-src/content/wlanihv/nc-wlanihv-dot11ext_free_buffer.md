---
UID: NC:wlanihv.DOT11EXT_FREE_BUFFER
title: DOT11EXT_FREE_BUFFER
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extfreebuffer.htm
old-project: netvista
ms.assetid: a6e49914-29c0-47d2-936b-17c48958cb36
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
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
req.alt-api: Dot11ExtFreeBuffer
req.alt-loc: wlanihv.h
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
req.typenames: *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_FREE_BUFFER callback



## -description

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
    <a href="netvista.native_802_11_ihv_handler_functions">Native 802.11 IHV Handler
    Functions</a>.


## -see-also
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>
</dt>
<dt>
<a href="netvista.native_802_11_ihv_handler_functions">Native 802.11 IHV Handler
   Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_FREE_BUFFER callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

