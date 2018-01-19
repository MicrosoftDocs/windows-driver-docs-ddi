---
UID: NE:wlanihv._DOT11_MSONEX_RESULT
title: _DOT11_MSONEX_RESULT
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_msonex_result.htm
old-project: netvista
ms.assetid: d5870125-2c0f-4cb9-ad2a-dc4939745504
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_MSONEX_RESULT, *PDOT11_MSONEX_RESULT, DOT11_MSONEX_RESULT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_MSONEX_RESULT
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
req.typenames: *PDOT11_MSONEX_RESULT, DOT11_MSONEX_RESULT
req.product: Windows 10 or later.
---

# _DOT11_MSONEX_RESULT enumeration



## -description

## -syntax

````
typedef enum _DOT11_MSONEX_RESULT { 
  DOT11_MSONEX_SUCCESS      = 0,
  DOT11_MSONEX_FAILURE      = 1,
  DOT11_MSONEX_IN_PROGRESS  = 2
} DOT11_MSONEX_RESULT, *PDOT11_MSONEX_RESULT;
````


## -enum-fields

### -field DOT11_MSONEX_SUCCESS

The 802.1X authentication operation succeeded.


### -field DOT11_MSONEX_FAILURE

The 802.1X authentication operation failed.


### -field DOT11_MSONEX_IN_PROGRESS

The 802.1X authentication operation is in progress.


## -remarks
After the IHV Extensions DLL initiates an 802.1X authentication operation, the operating system calls
    the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
    Dot11ExtIhvOneXIndicateResult</a> IHV handler function to complete the operation. When it calls this
    function, the operating system passes a DOT11_MSONEX_RESULT value to the 
    <i>OneXResult</i> parameter to specify the result of the authentication operation.


## -see-also
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
   Dot11ExtIhvOneXIndicateResult</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_MSONEX_RESULT enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

