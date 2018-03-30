---
UID: NF:wudfddi.IWDFDriverCreatedFile.Close
title: IWDFDriverCreatedFile::Close method
author: windows-driver-content
description: The Close method closes an instance of a UMDF driver-created-file object that was created by calling the IWDFDevice::CreateWdfFile method.
old-location: wdf\iwdfdrivercreatedfile_close.htm
old-project: wdf
ms.assetid: a9c1d1d7-4222-4c8c-92eb-497d13952bed
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Close method, Close method, IWDFDriverCreatedFile interface, Close,IWDFDriverCreatedFile.Close, IWDFDriverCreatedFile, IWDFDriverCreatedFile interface, Close method, IWDFDriverCreatedFile::Close, UMDFDriverCreatedFileObjectRef_52a9f370-6f1d-4d62-84de-0b56a61b95fc.xml, umdf.iwdfdrivercreatedfile_close, wdf.iwdfdrivercreatedfile_close, wudfddi/IWDFDriverCreatedFile::Close
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
-	IWDFDriverCreatedFile.Close
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDriverCreatedFile::Close method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Close</b> method closes an instance of a UMDF driver-created-file object that was created by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558828">IWDFDevice::CreateWdfFile</a> method.


## -parameters






## -returns



None




## -remarks



For more information, see <a href="https://msdn.microsoft.com/84b677b4-fddf-4f06-9ea6-e4642c3f1b2d">Creating and Using Driver-Created File Objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558828">IWDFDevice::CreateWdfFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558895">IWDFDriverCreatedFile</a>
 

 

