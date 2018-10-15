---
UID: NC:wlanihv.DOT11EXT_ALLOCATE_BUFFER
title: DOT11EXT_ALLOCATE_BUFFER
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extallocatebuffer.htm
tech.root: netvista
ms.assetid: 22c61f1d-027c-4e3e-af34-c513d4e1d0cc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXT_ALLOCATE_BUFFER, Dot11ExtAllocateBuffer, Dot11ExtAllocateBuffer callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_5f683d7c-9185-4786-9f39-2e397b93fbf0.xml, netvista.dot11extallocatebuffer, wlanihv/Dot11ExtAllocateBuffer
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
-	Dot11ExtAllocateBuffer
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_ALLOCATE_BUFFER callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtAllocateBuffer</b> function to allocate memory for variable-length
  buffers.


## -prototype


````
DWORD WINAPI * Dot11ExtAllocateBuffer(
  _In_  DWORD  dwByteCount,
  _Out_ LPVOID *ppvBuffer
);
````


## -parameters




### -param dwByteCount [in]

Size, in bytes, of the buffer to allocate.


### -param *ppvBuffer [out]

A pointer to a caller-supplied variable that stores the address of the allocated buffer. The
     <i>ppvBuffer</i> parameter has a valid non-null value if the return value is ERROR_SUCCESS.


## -returns



The call returns an ERROR_xxxx code defined in
     Winerror.h. The following ERROR_xxxx codes are commonly returned by the
     <b>Dot11ExtAllocateBuffer</b> function.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The call succeeded without an error.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The operating system was unable to allocate the memory due to a lack of resources.

</td>
</tr>
</table>
 




## -remarks



The IHV Extensions DLL must follow these guidelines when calling the
    <b>Dot11ExtAllocateBuffer</b> function.

<ul>
<li>
The IHV Extensions DLL must call this function when returning any variable-length buffer from an IHV
      Handler function. In this situation, the operating system is responsible for freeing the buffer after
      the return of the IHV Handler function.

For more information about the IHV Handler functions, see
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
      Functions</a>.

</li>
<li>
The IHV Extensions DLL might call this function to allocate memory referenced by the DLL itself.


In this situation, the DLL must free the memory buffer by calling
     <a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>.

</li>
</ul>



## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_create_discovery_profiles.md">
   Dot11ExtIhvCreateDiscoveryProfiles</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>



 

 


