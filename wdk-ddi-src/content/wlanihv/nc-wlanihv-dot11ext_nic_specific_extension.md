---
UID: NC:wlanihv.DOT11EXT_NIC_SPECIFIC_EXTENSION
title: DOT11EXT_NIC_SPECIFIC_EXTENSION (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extnicspecificextension.htm
tech.root: netvista
ms.assetid: e588db31-d6d7-4b79-80f5-128c6d618ab6
ms.date: 02/16/2018
ms.keywords: DOT11EXT_NIC_SPECIFIC_EXTENSION, Dot11ExtNicSpecificExtension, Dot11ExtNicSpecificExtension callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_cab7d3ba-3192-4fb5-8827-f0c4b77bcb20.xml, netvista.dot11extnicspecificextension, wlanihv/Dot11ExtNicSpecificExtension
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wlanihv.h
api_name:
- Dot11ExtNicSpecificExtension
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_NIC_SPECIFIC_EXTENSION callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div>

The IHV Extensions DLL calls the
  <b>Dot11ExtNicSpecificExtension</b> function to issue proprietary NDIS 6.0 method
  requests to the Native 802.11 miniport driver that manages a wireless LAN (WLAN) adapter.


## -prototype


```cpp
DWORD WINAPI * Dot11ExtNicSpecificExtension(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_     DWORD  dwInBufferSize,
  _In_     LPVOID pvInBuffer,
  _Inout_  DWORD  *pdwOutBufferSize,
  _Out_    LPVOID pvOutBuffer
);
```


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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-nic-specific-extension">
    OID_DOT11_NIC_SPECIFIC_EXTENSION</a> object identifier (OID).

<div class="alert"><b>Note</b>  OID_DOT11_NIC_SPECIFIC_EXTENSION is an optional OID for support by the Native
    802.11 miniport driver. If the driver does not support this OID,
    <b>Dot11ExtNicSpecificExtension</b> will return a value of ERROR_NOT_SUPPORTED.</div>


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-nic-specific-extension">
   OID_DOT11_NIC_SPECIFIC_EXTENSION</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 


