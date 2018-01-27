---
UID: NS:printoem._PUBLISHERINFO
title: _PUBLISHERINFO
author: windows-driver-content
description: The PUBLISHERINFO structure is used as an input parameter to the IPrintOemPS::GetInfo method.
old-location: print\publisherinfo.htm
old-project: print
ms.assetid: 6749b2e8-a9db-48a3-96e1-8592bcfa580d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PPUBLISHERINFO structure pointer [Print Devices], PPUBLISHERINFO, PUBLISHERINFO structure [Print Devices], PUBLISHERINFO, *PPUBLISHERINFO, printoem/PUBLISHERINFO, printoem/PPUBLISHERINFO, _PUBLISHERINFO, print_unidrv-pscript_rendering_dbd3e74a-00bd-4c21-80e5-80b788f83bb2.xml, print.publisherinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	printoem.h
apiname: 
-	PUBLISHERINFO
product: Windows
targetos: Windows
req.typenames: *PPUBLISHERINFO, PUBLISHERINFO
req.product: Windows 10 or later.
---

# _PUBLISHERINFO structure


## -description


The PUBLISHERINFO structure is used as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553221">IPrintOemPS::GetInfo</a> method.


## -syntax


````
typedef struct _PUBLISHERINFO {
  DWORD dwMode;
  WORD  wMinoutlinePPEM;
  WORD  wMaxbitmapPPEM;
} PUBLISHERINFO, *PPUBLISHERINFO;
````


## -struct-fields




### -field dwMode

Is a set of bit flags. The only flag defined is OEM_MODE_PUBLISHER, which must be set if a rendering plug-in for Pscript5 is using "publishing mode".


### -field wMinoutlinePPEM

Specifies the minimum font size, in pixels, for which the Pscript5 driver will download TrueType fonts as outline (Type 1) fonts. A font smaller than the minimum setting will be downloaded as a bitmap (Type 3) font.


### -field wMaxbitmapPPEM

Specifies the maximum font size, in pixels, for which the Pscript5 driver will download TrueType fonts as bitmap (Type 3) fonts. A font larger than the maximum setting will be downloaded as an outline (Type 1) font.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553221">IPrintOemPS::GetInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PUBLISHERINFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

