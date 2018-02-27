---
UID: NS:wwan._WWAN_VENDOR_SPECIFIC
title: "_WWAN_VENDOR_SPECIFIC"
author: windows-driver-content
description: The WWAN_VENDOR_SPECIFIC structure represents vendor-specific data.
old-location: netvista\wwan_vendor_specific.htm
old-project: netvista
ms.assetid: e3f024d0-4543-4c28-958f-58a3072027ad
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWWAN_VENDOR_SPECIFIC, PWWAN_VENDOR_SPECIFIC, PWWAN_VENDOR_SPECIFIC structure pointer [Network Drivers Starting with Windows Vista], WWAN_VENDOR_SPECIFIC, WWAN_VENDOR_SPECIFIC structure [Network Drivers Starting with Windows Vista], WwanRef_9261cb07-079e-4266-8358-fff73af8c31a.xml, _WWAN_VENDOR_SPECIFIC, netvista.wwan_vendor_specific, wwan/PWWAN_VENDOR_SPECIFIC, wwan/WWAN_VENDOR_SPECIFIC"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_VENDOR_SPECIFIC
product: Windows
targetos: Windows
req.typenames: WWAN_VENDOR_SPECIFIC, *PWWAN_VENDOR_SPECIFIC
req.product: Windows 10 or later.
---

# _WWAN_VENDOR_SPECIFIC structure


## -description


The WWAN_VENDOR_SPECIFIC structure represents vendor-specific data.


## -syntax


````
typedef struct _WWAN_VENDOR_SPECIFIC {
  ULONG uVendorSpecificBufferSize;
} WWAN_VENDOR_SPECIFIC, *PWWAN_VENDOR_SPECIFIC;
````


## -struct-fields




### -field uVendorSpecificBufferSize

The size, in bytes, of the vendor-specific buffer that follows the structure instance in
     memory.


## -remarks



NDIS_WWAN_VENDOR_SPECIFIC should have the data following the 
    <b>uVendorSpecificBufferSize</b> member.




## -see-also

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_vendor_specific.md">NDIS_WWAN_VENDOR_SPECIFIC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_VENDOR_SPECIFIC structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

