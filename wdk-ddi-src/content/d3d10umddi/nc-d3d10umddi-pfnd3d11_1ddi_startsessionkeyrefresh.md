---
UID: NC:d3d10umddi.PFND3D11_1DDI_STARTSESSIONKEYREFRESH
title: PFND3D11_1DDI_STARTSESSIONKEYREFRESH
author: windows-driver-content
description: Gets a random number that can be used to refresh the session key.
old-location: display\startsessionkeyrefresh1.htm
old-project: display
ms.assetid: 0973cef3-41a8-495e-aa8a-ce64df53b892
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11_1DDI_STARTSESSIONKEYREFRESH, d3d10umddi/pfnStartSessionKeyRefresh, display.startsessionkeyrefresh1, pfnStartSessionKeyRefresh, pfnStartSessionKeyRefresh callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	pfnStartSessionKeyRefresh
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_STARTSESSIONKEYREFRESH callback


## -description


Gets a random number that can be used to refresh the session key.




## -prototype


````
PFND3D11_1DDI_STARTSESSIONKEYREFRESH pfnStartSessionKeyRefresh;

VOID APIENTRY* pfnStartSessionKeyRefresh(
  _In_    D3D10DDI_HDEVICE          hDevice,
  _In_    D3D11_1DDI_HCRYPTOSESSION hCryptoSession,
  _Inout_ UINT                      RandomNumberSize,
  _In_    VOID                      *pRandomNumber
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param hCryptoSession [in]

A handle to the cryptographic session object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a> function.




### -param RandomNumberSize [in, out]

The size, in bytes, of the number in the buffer that is referenced by the <i>pRandomNumber</i> parameter.



### -param *pRandomNumber [in]

A pointer to a buffer that contains the status sequence number for the random start.



## -returns



This callback function does not return a value.




## -remarks



The hardware and driver can optionally support <b>StartSessionKeyRefresh</b> for all cryptographic types.



When the Microsoft Direct3D runtime calls the driver's <b>StartSessionKeyRefresh</b> function, the driver generates and saves a random number and returns it in the buffer that the <i>pRandomNumber</i> parameter points to.

When the runtime subsequently calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a> function, the driver refreshes the session key by performing an XOR operation of the random number with the key.






## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_STARTSESSIONKEYREFRESH callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

