---
UID: NS:windot11._DOT11_STATUS_INDICATION
title: _DOT11_STATUS_INDICATION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_status_indication.htm
old-project: netvista
ms.assetid: 77b2eae8-1fa5-4f87-97e4-713bfca627b2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_STATUS_INDICATION, DOT11_STATUS_INDICATION, *PDOT11_STATUS_INDICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_STATUS_INDICATION
req.alt-loc: windot11.h
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
req.typenames: DOT11_STATUS_INDICATION, *PDOT11_STATUS_INDICATION
req.product: Windows 10 or later.
---

# _DOT11_STATUS_INDICATION structure



## -description

## -syntax

````
typedef struct _DOT11_STATUS_INDICATION {
  ULONG       uStatusType;
  NDIS_STATUS ndisStatus;
} DOT11_STATUS_INDICATION, *PDOT11_STATUS_INDICATION;
````


## -struct-fields

### -field uStatusType

The type of status indication that is made by the miniport driver.
     

For more information about the value that is used for the 
     <b>uStatusType</b> member, see the topic for the OID that requires a completion indication that uses the
     DOT11_STATUS_INDICATION structure.


### -field ndisStatus

An NDIS_STATUS value that indicates the result of the operation.
     

If the operation completed without a failure, the miniport driver must set the 
     <b>ndisStatus</b> member to NDIS_STATUS_SUCCESS. Otherwise, the driver must set 
     <b>ndisStatus</b> to the appropriate NDIS_STATUS_xxx value for the failure.


## -remarks
For the Windows Vista operating system, only 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a> requires the
    use of the DOT11_STATUS_INDICATION structure for completion indications.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569409">OID_DOT11_RESET_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_STATUS_INDICATION structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

