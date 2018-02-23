---
UID: NC:wlanihv.DOT11EXTIHV_CONTROL
title: DOT11EXTIHV_CONTROL
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvcontrol.htm
old-project: netvista
ms.assetid: 27e1f112-a961-4464-9048-b56394930453
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.dot11extihvcontrol, Dot11ExtIhvControl callback function [Network Drivers Starting with Windows Vista], Dot11ExtIhvControl, DOT11EXTIHV_CONTROL, DOT11EXTIHV_CONTROL, wlanihv/Dot11ExtIhvControl, Native_802.11_IHV_Ext_49f041a3-e60a-4d60-92e2-9c12a4c1db5d.xml
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
-	Wlanihv.h
apiname:
-	Dot11ExtIhvControl
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_CONTROL callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the IHV Extensions DLL 
  <i>Dot11ExtIhvControl</i> function to allow independent hardware vendor (IHV) control of WLAN drivers or
  services.


## -prototype


````
DOT11EXTIHV_CONTROL Dot11ExtIhvControl;

DWORD APIENTRY Dot11ExtIhvControl(
  _In_opt_  HANDLE hIhvExtAdapter,
  _In_      DWORD  dwInBufferSize,
  _In_opt_  PBYTE  pInBuffer,
  _In_      DWORD  dwOutBufferSize,
  _Out_opt_ PBYTE  pOutBuffer,
  _Out_     DWORD  pdwBytesReturned
)
{ ... }
````


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV Handler function.


### -param dwInBufferSize [in]

The size, in bytes, of the input control buffer pointed to by the 
     <i>pInBuffer</i> parameter.


### -param pInBuffer [in, optional]

A pointer to the input control buffer.


### -param dwOutBufferSize [in]

The size, in bytes, of the output buffer (if provided) pointed to by the 
     <i>pOutBuffer</i> parameter.


### -param pOutBuffer [out, optional]

A pointer to the output buffer, if provided.


### -param pdwBytesReturned [out]

A pointer to a variable that contains the size, in bytes, of the response input/output
     buffer.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.




## -remarks



The operating system calls this function when the 
    <b>WlanIhvControl</b> function is called with the 
    <i>Type</i> parameter set to a value of 
    <b>wlan_ihv_control_type_service</b>. For a description of the 
    <b>WlanIhvControl</b> function, see the Microsoft Windows SDK documentation.

Data transferred with this function is not validated, so the IHV is responsible for correctly parsing
    the input buffer.

The data buffer pointed to by the 
    <i>pdwBytesReturned</i> parameter will always be returned. However, the buffer pointed to by 
    <i>pOutBuffer</i> will be copied only if a valid pointer is provided and the value pointed to by 
    <i>pdwBytesReturned</i> is less than or equal to 
    <i>dwOutBufferSize</i> .




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_CONTROL callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

