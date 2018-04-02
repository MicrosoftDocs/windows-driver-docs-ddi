---
UID: NF:wudfddi.IWDFDriver.RetrieveVersionString
title: IWDFDriver::RetrieveVersionString method
author: windows-driver-content
description: The RetrieveVersionString method retrieves the version of the framework.
old-location: wdf\iwdfdriver_retrieveversionstring.htm
old-project: wdf
ms.assetid: 2fa320df-bafd-42f4-a0a1-14151c39d68a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFDriver, IWDFDriver interface, RetrieveVersionString method, IWDFDriver::RetrieveVersionString, RetrieveVersionString method, RetrieveVersionString method, IWDFDriver interface, RetrieveVersionString,IWDFDriver.RetrieveVersionString, UMDFDriverObjectRef_fea0fb04-a861-44b6-8552-150454f9933d.xml, umdf.iwdfdriver_retrieveversionstring, wdf.iwdfdriver_retrieveversionstring, wudfddi/IWDFDriver::RetrieveVersionString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDriver.RetrieveVersionString
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDriver::RetrieveVersionString method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveVersionString</b> method retrieves the version of the framework.


## -parameters




### -param pVersion [out]

A pointer to a buffer that receives a <b>NULL</b>-terminated string that represents the version of the framework if the supplied buffer is non-<b>NULL</b> and <b>RetrieveVersionString</b> is successful. 


### -param pdwVersionLength [in, out]

A pointer to a variable that receives the size, in characters, of the version string that <i>pVersion</i> points to. On input, this variable contains the size, in bytes, of the buffer at <i>pVersion</i>.

If the buffer at <i>pVersion</i> is <b>NULL</b>, the value that the driver supplies is zero. The framework then returns the size, in characters, that is required for the version string.

If the buffer at <i>pVersion</i> is non-<b>NULL</b>, the framework returns the size, in characters, of the version string.


## -returns



<b>RetrieveVersionString</b> returns S_OK for the following scenarios:


<ul>
<li>
The buffer that the <i>pVersion</i> parameter points to was non-<b>NULL</b> and large enough to hold the version string, including the <b>NULL</b> character. In addition, the framework successfully copied the string into the supplied buffer and set the variable that is pointed to by the <i>pdwVersionLength</i> parameter to the number of characters in the string.

</li>
<li>
The buffer at <i>pVersion</i> was <b>NULL</b>, the driver preset the variable at <i>pdwVersionLength</i> to 0, and the framework set the variable at <i>pdwVersionLength</i> to the number of characters that are required for the string. 


</li>
</ul><b>RetrieveVersionString</b> returns HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER) to indicate that the supplied buffer is non-<b>NULL</b> and did not contain enough space to hold the version. The framework sets the variable at <i>pdwVersionLength</i> to the number of characters that are required for the string.



<b>RetrieveVersionString</b> might also return other HRESULT values.





