---
UID: NC:wlanihv.DOT11EXT_NIC_SPECIFIC_EXTENSION
title: DOT11EXT_NIC_SPECIFIC_EXTENSION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extnicspecificextension.htm
old-project: netvista
ms.assetid: e588db31-d6d7-4b79-80f5-128c6d618ab6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXT_NIC_SPECIFIC_EXTENSION, Dot11ExtNicSpecificExtension, Dot11ExtNicSpecificExtension callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_cab7d3ba-3192-4fb5-8827-f0c4b77bcb20.xml, netvista.dot11extnicspecificextension, wlanihv/Dot11ExtNicSpecificExtension
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
-	Dot11ExtNicSpecificExtension
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_NIC_SPECIFIC_EXTENSION callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtNicSpecificExtension</b> function to issue proprietary NDIS 6.0 method
  requests to the Native 802.11 miniport driver that manages a wireless LAN (WLAN) adapter.


## -prototype


````
DWORD WINAPI * Dot11ExtNicSpecificExtension(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_     DWORD  dwInBufferSize,
  _In_     LPVOID pvInBuffer,
  _Inout_  DWORD  *pdwOutBufferSize,
  _Out_    LPVOID pvOutBuffer
);
````


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param dwInBufferSize [in]

The size, in bytes, of the caller-allocated data buffer referenced by the 
     <i>pvInBuffer</i> parameter.


### -param pvInBuffer [in]

A pointer to a caller-allocated input buffer that contains the data required to perform the
     operation. The format of this data is defined by the IHV.


### -param *pdwOutBufferSize [in, out]

A pointer to a caller-allocated DWORD variable. When the 
     <b>Dot11ExtNicSpecificExtension</b> function is called, the IHV Extensions DLL
     must set this variable to the size, in bytes, of the caller-allocated data buffer referenced by the 
     <i>pvOutBuffer</i> parameter. When the function returns, the operating system sets the variable to the
     actual number of bytes returned in the data buffer referenced by the 
     <i>pvOutBuffer</i> parameter.


### -param pvOutBuffer [out]

A pointer to a caller-allocated buffer that contains data returned from the Native 802.11 miniport
     driver for the specified request. The format of this data is defined by the IHV. This parameter can be
     <b>NULL</b> if data is not to be returned by the Native 802.11 miniport driver.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.




## -remarks



The 
    <b>Dot11ExtNicSpecificExtension</b> function allows the IHV Extensions DLL to
    pass proprietary method requests to the Native 802.11 miniport driver, which is referenced by the 
    <i>hDot11SvcHandle</i> parameter. The operating system issues the method request through the Native 802.11
    
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-nic-specific-extension">
    OID_DOT11_NIC_SPECIFIC_EXTENSION</a> object identifier (OID).

<div class="alert"><b>Note</b>  OID_DOT11_NIC_SPECIFIC_EXTENSION is an optional OID for support by the Native
    802.11 miniport driver. If the driver does not support this OID, 
    <b>Dot11ExtNicSpecificExtension</b> will return a value of ERROR_NOT_SUPPORTED.</div>
<div> </div>



## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-nic-specific-extension">
   OID_DOT11_NIC_SPECIFIC_EXTENSION</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_NIC_SPECIFIC_EXTENSION callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

