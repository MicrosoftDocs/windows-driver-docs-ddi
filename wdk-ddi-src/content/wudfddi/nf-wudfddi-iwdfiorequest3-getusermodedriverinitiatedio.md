---
UID: NF:wudfddi.IWDFIoRequest3.GetUserModeDriverInitiatedIo
title: IWDFIoRequest3::GetUserModeDriverInitiatedIo
author: windows-driver-content
description: The GetUserModeDriverInitiatedIo method determines whether an I/O request is marked as initiated by a UMDF driver.
old-location: wdf\iwdfiorequest3_getusermodedriverinitiatedio.htm
tech.root: wdf
ms.assetid: 41C4E9D2-DC1B-4DFC-8C15-E9C21515B5F0
ms.date: 02/26/2018
ms.keywords: GetUserModeDriverInitiatedIo, GetUserModeDriverInitiatedIo method, GetUserModeDriverInitiatedIo method,IWDFIoRequest3 interface, IWDFIoRequest3 interface,GetUserModeDriverInitiatedIo method, IWDFIoRequest3.GetUserModeDriverInitiatedIo, IWDFIoRequest3::GetUserModeDriverInitiatedIo, umdf.iwdfiorequest3_getusermodedriverinitiatedio, wdf.iwdfiorequest3_getusermodedriverinitiatedio, wudfddi/IWDFIoRequest3::GetUserModeDriverInitiatedIo
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
-	IWDFIoRequest3.GetUserModeDriverInitiatedIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest3::GetUserModeDriverInitiatedIo


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The 
  <b>GetUserModeDriverInitiatedIo</b> method determines whether an I/O request is marked as initiated by a UMDF driver.


## -parameters






## -returns



The method returns <b>TRUE</b> if the request is marked as UMDF driver-initiated and <b>FALSE</b> if the request is not marked as UMDF driver-initiated.




## -remarks



For additional information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451354">SetUserModeDriverInitiatedIo</a>.

The UMDF 2 equivalent of this method is <a href="https://msdn.microsoft.com/library/windows/hardware/dn265618">WdfRequestGetUserModeInitiatedIo</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451337">IWDFIoRequest3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451354">SetUserModeDriverInitiatedIo</a>
 

 

