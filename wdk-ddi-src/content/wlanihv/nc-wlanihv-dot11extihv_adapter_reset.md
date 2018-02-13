---
UID: NC:wlanihv.DOT11EXTIHV_ADAPTER_RESET
title: DOT11EXTIHV_ADAPTER_RESET
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvadapterreset.htm
old-project: netvista
ms.assetid: c1e8cce7-6fa4-45d3-a8c8-9f2ef0a8e846
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extihvadapterreset, Dot11ExtIhvAdapterReset callback function [Network Drivers Starting with Windows Vista], Dot11ExtIhvAdapterReset, DOT11EXTIHV_ADAPTER_RESET, DOT11EXTIHV_ADAPTER_RESET, wlanihv/Dot11ExtIhvAdapterReset, Native_802.11_IHV_Ext_1749484b-7d42-42c0-bae2-5de47406f26b.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wlanihv.h
apiname:
-	Dot11ExtIhvAdapterReset
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_ADAPTER_RESET callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the IHV Extensions DLL 
  <i>Dot11ExtIhvAdapterReset</i> function to reset the wireless LAN (WLAN) adapter.


## -prototype


````
DOT11EXTIHV_ADAPTER_RESET Dot11ExtIhvAdapterReset;

DWORD APIENTRY Dot11ExtIhvAdapterReset(
  _In_opt_ HANDLE hIhvExtAdapter
)
{ ... }
````


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.




## -remarks



The operating system calls 
    <i>Dot11ExtIhvAdapterReset</i> whenever one of the following events occurs.

<ul>
<li>
The WLAN adapter performs a disconnection operation. For more information about this operation, see 
      <a href="https://msdn.microsoft.com/f0ccdd41-3470-4602-a26b-af166e7eac82">Disconnection Operations</a>.

</li>
<li>
The operating system resets the Native 802.11 miniport driver, which manages the adapter, through a
      set request of 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>.

</li>
</ul>
The 
    <i>Dot11ExtIhvAdapterReset</i> function must restore the WLAN adapter to the same state as when the DLL's 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> function
    was called.

For more information about the reset operation for WLAN adapters, see 
    <a href="https://msdn.microsoft.com/1f993977-b4a1-42ec-8de3-2f4855db93a7">802.11 WLAN Adapter Reset</a>.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_ADAPTER_RESET callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

