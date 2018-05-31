---
UID: NC:wlanihv.DOT11EXTIHV_DEINIT_SERVICE
title: DOT11EXTIHV_DEINIT_SERVICE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvdeinitservice.htm
old-project: netvista
ms.assetid: 5ee52306-4229-4d81-af1f-6eb37f41ad41
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXTIHV_DEINIT_SERVICE, Dot11ExtIhvDeinitService, Dot11ExtIhvDeinitService callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_02e9e301-f950-47e3-9a1f-4212ae55387e.xml, netvista.dot11extihvdeinitservice, wlanihv/Dot11ExtIhvDeinitService
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
-	Wlanihv.h
api_name:
-	Dot11ExtIhvDeinitService
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_DEINIT_SERVICE callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the 
  <i>Dot11ExtIhvDeinitService</i> function to halt the IHV Extensions DLL.


## -prototype


````
DOT11EXTIHV_DEINIT_SERVICE Dot11ExtIhvDeinitService;

VOID APIENTRY Dot11ExtIhvDeinitService(
   VOID 
)
{ ... }
````


## -parameters



## -returns



None




## -remarks



When the 
    <i>Dot11ExtIhvDeinitService</i> function is called, the IHV Extensions DLL must be brought to a state that
    it can safely be unloaded by the operating system. The DLL must follow these guidelines when this
    function is called.

<ul>
<li>
The operating system calls the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">
      Dot11ExtIhvDeinitAdapter</a> function prior to calling the 
      <i>Dot11ExtIhvDeinitService</i> function. As a result, the 
      <i>Dot11ExtIhvDeinitService</i> function should not initiate any operations on the WLAN adapter.
      Instead, 
      <i>Dot11ExtIhvDeinitService</i> should prepare the DLL to be unloaded by the operating system.

</li>
<li>
The DLL must terminate all executing threads that it created. The DLL must not return from the 
      <i>Dot11ExtIhvDeinitService</i> function call until all threads have been terminated.

</li>
<li>
The DLL must free any allocated resources for the DLL itself. In particular, all memory the DLL
      allocated through calls to 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a> must be
      freed through calls to 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>.

</li>
</ul>



## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>



 

 


