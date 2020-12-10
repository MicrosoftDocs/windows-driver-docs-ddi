---
UID: NE:wlanihv._DOT11_MSONEX_RESULT
title: _DOT11_MSONEX_RESULT (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_msonex_result.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_MSONEX_RESULT enumeration"]
ms.keywords: "*PDOT11_MSONEX_RESULT, DOT11_MSONEX_FAILURE, DOT11_MSONEX_IN_PROGRESS, DOT11_MSONEX_RESULT, DOT11_MSONEX_RESULT enumeration [Network Drivers Starting with Windows Vista], DOT11_MSONEX_SUCCESS, Native_802.11_data_types_504c48c9-585e-408b-bb8f-6668cddd7eff.xml, PDOT11_MSONEX_RESULT, PDOT11_MSONEX_RESULT enumeration pointer [Network Drivers Starting with Windows Vista], _DOT11_MSONEX_RESULT, netvista.dot11_msonex_result, wlanihv/DOT11_MSONEX_FAILURE, wlanihv/DOT11_MSONEX_IN_PROGRESS, wlanihv/DOT11_MSONEX_RESULT, wlanihv/DOT11_MSONEX_SUCCESS, wlanihv/PDOT11_MSONEX_RESULT"
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
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
targetos: Windows
req.typenames: DOT11_MSONEX_RESULT, *PDOT11_MSONEX_RESULT
req.product: Windows 10 or later.
f1_keywords:
 - _DOT11_MSONEX_RESULT
 - wlanihv/_DOT11_MSONEX_RESULT
 - PDOT11_MSONEX_RESULT
 - wlanihv/PDOT11_MSONEX_RESULT
 - DOT11_MSONEX_RESULT
 - wlanihv/DOT11_MSONEX_RESULT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wlanihv.h
api_name:
 - DOT11_MSONEX_RESULT
---

# _DOT11_MSONEX_RESULT enumeration


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_MSONEX_RESULT enumeration defines the results of the 802.1X authentication operation
  performed by the operating system through a call to the
  <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a> function.

## -enum-fields

### -field DOT11_MSONEX_SUCCESS

The 802.1X authentication operation succeeded.

### -field DOT11_MSONEX_FAILURE

The 802.1X authentication operation failed.

### -field DOT11_MSONEX_IN_PROGRESS

The 802.1X authentication operation is in progress.

## -syntax

```cpp
typedef enum _DOT11_MSONEX_RESULT {
  DOT11_MSONEX_SUCCESS      = 0,
  DOT11_MSONEX_FAILURE      = 1,
  DOT11_MSONEX_IN_PROGRESS  = 2
} DOT11_MSONEX_RESULT, *PDOT11_MSONEX_RESULT;
```

## -remarks

After the IHV Extensions DLL initiates an 802.1X authentication operation, the operating system calls
    the
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
    Dot11ExtIhvOneXIndicateResult</a> IHV handler function to complete the operation. When it calls this
    function, the operating system passes a DOT11_MSONEX_RESULT value to the
    <i>OneXResult</i> parameter to specify the result of the authentication operation.

## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
   Dot11ExtIhvOneXIndicateResult</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a>
