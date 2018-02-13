---
UID: NF:wudfddi.IWDFIoRequestCompletionParams.GetIoctlParameters
title: IWDFIoRequestCompletionParams::GetIoctlParameters method
author: windows-driver-content
description: The GetIoctlParameters method retrieves parameters that are associated with the completion of a device I/O control request.
old-location: wdf\iwdfiorequestcompletionparams_getioctlparameters.htm
old-project: wdf
ms.assetid: 59e2cd27-ec10-46e9-aa0d-4a00e2684e76
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFIoRequestCompletionParams, GetIoctlParameters method, UMDFRequestObjectRef_7d375866-617c-418f-b449-7931a88e7ae4.xml, IWDFIoRequestCompletionParams interface, GetIoctlParameters method, wdf.iwdfiorequestcompletionparams_getioctlparameters, umdf.iwdfiorequestcompletionparams_getioctlparameters, wudfddi/IWDFIoRequestCompletionParams::GetIoctlParameters, GetIoctlParameters method, IWDFIoRequestCompletionParams interface, IWDFIoRequestCompletionParams::GetIoctlParameters, GetIoctlParameters
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoRequestCompletionParams.GetIoctlParameters
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFIoRequestCompletionParams::GetIoctlParameters method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetIoctlParameters</b> method retrieves parameters that are associated with the completion of a device I/O control request.


## -syntax


````
void GetIoctlParameters(
  [out, optional] ULONG      *pIoControlCode,
  [out, optional] IWDFMemory **ppInputMemory,
  [out, optional] SIZE_T     *pInputMemoryOffset,
  [out, optional] IWDFMemory **ppOutputMemory,
  [out, optional] SIZE_T     *pOutputMemoryOffset,
  [out, optional] SIZE_T     *pOutBytes
);
````


## -parameters




### -param pIoControlCode [out, optional]

A pointer to a variable that receives the control code that identifies the specific operation to be performed. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param ppInputMemory [out, optional]

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface for access to the input buffer for the completion of the device I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pInputMemoryOffset [out, optional]

A pointer to a variable that receives the offset, in bytes, into the input buffer for the completion of the I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param ppOutputMemory [out, optional]

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface for access to the output buffer for the completion of the device I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pOutputMemoryOffset [out, optional]

A pointer to a variable that receives the offset, in bytes, into the output buffer for the completion of the I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pOutBytes [out, optional]

A pointer to a variable that receives the number of bytes that are output for the completion of the device I/O control request.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -returns



None




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequestcompletionparams.md">IWDFIoRequestCompletionParams</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequestCompletionParams::GetIoctlParameters method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

