---
UID: NC:wlanihv.DOT11EXTIHV_DEINIT_SERVICE
title: DOT11EXTIHV_DEINIT_SERVICE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvdeinitservice.htm
old-project: netvista
ms.assetid: 5ee52306-4229-4d81-af1f-6eb37f41ad41
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
req.alt-api: Dot11ExtIhvDeinitService
req.alt-loc: Wlanihv.h
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

# DOT11EXTIHV_DEINIT_SERVICE callback



## -description

## -prototype

````
DOT11EXTIHV_DEINIT_SERVICE Dot11ExtIhvDeinitService;

VOID APIENTRY Dot11ExtIhvDeinitService(
   VOID 
)
{ ... }
````


## -parameters

### -param  

None


## -returns
None


## -remarks
When the 
    <i>Dot11ExtIhvDeinitService</i> function is called, the IHV Extensions DLL must be brought to a state that
    it can safely be unloaded by the operating system. The DLL must follow these guidelines when this
    function is called.

The operating system calls the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">
      Dot11ExtIhvDeinitAdapter</a> function prior to calling the 
      <i>Dot11ExtIhvDeinitService</i> function. As a result, the 
      <i>Dot11ExtIhvDeinitService</i> function should not initiate any operations on the WLAN adapter.
      Instead, 
      <i>Dot11ExtIhvDeinitService</i> should prepare the DLL to be unloaded by the operating system.

The DLL must terminate all executing threads that it created. The DLL must not return from the 
      <i>Dot11ExtIhvDeinitService</i> function call until all threads have been terminated.

The DLL must free any allocated resources for the DLL itself. In particular, all memory the DLL
      allocated through calls to 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a> must be
      freed through calls to 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>.


## -see-also
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_DEINIT_SERVICE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

