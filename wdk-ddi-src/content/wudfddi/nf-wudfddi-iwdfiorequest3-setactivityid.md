---
UID: NF:wudfddi.IWDFIoRequest3.SetActivityId
title: IWDFIoRequest3::SetActivityId method
author: windows-driver-content
description: The SetActivityId method associates an activity identifier with an I/O request.
old-location: wdf\iwdfiorequest3_setactivityid.htm
old-project: wdf
ms.assetid: 57CB3CED-FE46-4A74-9E23-82640B7EF1DC
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoRequest3, IWDFIoRequest3 interface, SetActivityId method, IWDFIoRequest3::SetActivityId, SetActivityId method, SetActivityId method, IWDFIoRequest3 interface, SetActivityId,IWDFIoRequest3.SetActivityId, umdf.iwdfiorequest3_setactivityid, wdf.iwdfiorequest3_setactivityid, wudfddi/IWDFIoRequest3::SetActivityId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
-	IWDFIoRequest3.SetActivityId
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest3::SetActivityId method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The 
  <b>SetActivityId</b> method associates an activity identifier with an I/O request.


## -parameters




### -param ActivityId [in]

A pointer to the activity identifier GUID to store in the I/O request.


## -returns



This method does not return a value.




## -remarks



Calling <b>SetActivityId</b> does not set an association with any previously present activity identifier. When the driver calls <b>SetActivityId</b>, any existing activity identifier is overwritten.

To set an association, retrieve the existing identifier by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451345">RetrieveActivityId</a> and then associate the existing identifier with the new one by calling <a href="https://msdn.microsoft.com/798cf3ba-e1cc-4eaf-a1d2-2313a64aab1a">EventWriteTransfer</a>.

The framework does not clear a request's activity identifier when the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559048">IWdfIoRequest2::Reuse</a>.

For more information about activity identifiers, see <a href="https://msdn.microsoft.com/2B70953F-5192-4654-9506-6A84373D20B4">Using Activity Identifiers</a>.

The UMDF 2 equivalent of this method is <a href="https://msdn.microsoft.com/library/windows/hardware/dn265622">WdfRequestSetActivityId</a>.


#### Examples

For a code example that uses <b>SetActivityId</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451345">RetrieveActivityId</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451337">IWDFIoRequest3</a>



<a href="https://msdn.microsoft.com/A90FCF3C-B648-4E97-887E-FCE58D7FA13A">IWDFIoRequest3::RetrieveActivityId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265622">WdfRequestSetActivityId</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest3::SetActivityId method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

