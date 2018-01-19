---
UID: NF:wudfddi.IWDFMemory.GetDataBuffer
title: IWDFMemory::GetDataBuffer method
author: windows-driver-content
description: The GetDataBuffer method retrieves the data buffer that is associated with a memory object.
old-location: wdf\iwdfmemory_getdatabuffer.htm
old-project: wdf
ms.assetid: 136aa2af-e3bf-48b6-9511-348510eedfb5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFMemory, IWDFMemory::GetDataBuffer, GetDataBuffer
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
req.alt-api: IWDFMemory.GetDataBuffer
req.alt-loc: WUDFx.dll
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
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFMemory::GetDataBuffer method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDataBuffer</b> method retrieves the data buffer that is associated with a memory object.



## -syntax

````
void* GetDataBuffer(
  [out, optional] SIZE_T *pBufferSize
);
````


## -parameters

### -param pBufferSize [out, optional]

A pointer to a variable that receives information that describes the size of the data buffer.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -returns
<b>GetDataBuffer</b> returns a pointer to the data buffer.


## -remarks
For a code example of how to use the <b>GetDataBuffer</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFMemory::GetDataBuffer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

