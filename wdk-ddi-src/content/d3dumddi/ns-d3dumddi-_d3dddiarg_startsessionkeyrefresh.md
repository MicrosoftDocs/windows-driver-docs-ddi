---
UID: NS:d3dumddi._D3DDDIARG_STARTSESSIONKEYREFRESH
title: "_D3DDDIARG_STARTSESSIONKEYREFRESH"
author: windows-driver-content
description: The D3DDDIARG_STARTSESSIONKEYREFRESH structure contains information about the random number for the encryption session.
old-location: display\d3dddiarg_startsessionkeyrefresh.htm
old-project: display
ms.assetid: f7494ea8-e639-4466-9d56-07d164f57b5b
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, A, D, D3DDDIARG_STARTSESSIONKEYREFRESH, D3DDDIARG_STARTSESSIONKEYREFRESH structure [Display Devices], E, F, G, H, I, K, N, O, R, S, T, UMDisplayDriver_param_Structs_63d20fb4-b769-45bf-8e3f-badb7b8e52e2.xml, Y, _, _D3DDDIARG_STARTSESSIONKEYREFRESH, d3dumddi/D3DDDIARG_STARTSESSIONKEYREFRESH, display.d3dddiarg_startsessionkeyrefresh"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_STARTSESSIONKEYREFRESH is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
apiname:
-	D3DDDIARG_STARTSESSIONKEYREFRESH
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_STARTSESSIONKEYREFRESH
---

# _D3DDDIARG_STARTSESSIONKEYREFRESH structure


## -description


The D3DDDIARG_STARTSESSIONKEYREFRESH structure contains information about the random number for the encryption session. 


## -syntax


````
typedef struct _D3DDDIARG_STARTSESSIONKEYREFRESH {
  HANDLE hCryptoSession;
  VOID   *pRandomNumber;
  UINT   RandomNumberSize;
} D3DDDIARG_STARTSESSIONKEYREFRESH;
````


## -struct-fields




### -field hCryptoSession

[in] A handle to the encryption session that is created in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function. 


### -field pRandomNumber

[out] A pointer to a buffer that contains the status sequence number for the random start. 


### -field RandomNumberSize

[in/out] The size, in bytes, of the number that the <b>pRandomNumber</b> member points to. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_STARTSESSIONKEYREFRESH structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

