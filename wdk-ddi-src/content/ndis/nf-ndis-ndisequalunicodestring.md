---
UID: NF:ndis.NdisEqualUnicodeString
title: NdisEqualUnicodeString macro
author: windows-driver-content
description: The NdisEqualUnicodeString function compares two Unicode strings and returns whether they are equal.
old-location: netvista\ndisequalunicodestring.htm
old-project: netvista
ms.assetid: 8f3abf40-bb47-4fa6-862b-6126edb00b36
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , E, N, NdisEqualUnicodeString, NdisEqualUnicodeString macro [Network Drivers Starting with Windows Vista], S, U, a, c, d, e, g, i, l, n, ndis/NdisEqualUnicodeString, ndis_string_ref_ccfcf1e6-b983-47a3-a46e-3a6ff1eb7158.xml, netvista.ndisequalunicodestring, o, q, r, s, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlEqualUnicodeString instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: ndis.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisEqualUnicodeString
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisEqualUnicodeString macro


## -description


The
  <b>NdisEqualUnicodeString</b> function compares two Unicode strings and returns whether they are
  equal.


## -syntax


````
BOOLEAN NdisEqualUnicodeString(
  [in] PNDIS_STRING String1,
  [in] PNDIS_STRING String2,
  [in] BOOLEAN      CaseInSensitive
);
````


## -parameters




### -param _String1 [in]

A pointer to an NDIS_STRING type that describes the first Unicode string.


### -param _String2 [in]

A pointer to an NDIS_STRING type that describes the second Unicode string.


### -param _CaseInsensitive

TBD






#### - CaseInSensitive [in]

A Boolean value that is <b>TRUE</b>, if case should be ignored when doing the comparison. Otherwise, it
     is <b>FALSE</b>.


## -remarks



Starting with Windows 2000 and later drivers, a string of type NDIS_STRING is a counted,
    null-terminated Unicode string. That is, NDIS defines the NDIS_STRING type as a 
    <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisEqualUnicodeString macro%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

