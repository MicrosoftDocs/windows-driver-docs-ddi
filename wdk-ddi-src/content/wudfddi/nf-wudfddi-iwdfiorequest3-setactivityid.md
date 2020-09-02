---
UID: NF:wudfddi.IWDFIoRequest3.SetActivityId
title: IWDFIoRequest3::SetActivityId (wudfddi.h)
description: The SetActivityId method associates an activity identifier with an I/O request.
old-location: wdf\iwdfiorequest3_setactivityid.htm
tech.root: wdf
ms.assetid: 57CB3CED-FE46-4A74-9E23-82640B7EF1DC
ms.date: 02/26/2018
keywords: ["IWDFIoRequest3::SetActivityId"]
ms.keywords: IWDFIoRequest3 interface,SetActivityId method, IWDFIoRequest3.SetActivityId, IWDFIoRequest3::SetActivityId, SetActivityId, SetActivityId method, SetActivityId method,IWDFIoRequest3 interface, umdf.iwdfiorequest3_setactivityid, wdf.iwdfiorequest3_setactivityid, wudfddi/IWDFIoRequest3::SetActivityId
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoRequest3::SetActivityId
 - wudfddi/IWDFIoRequest3::SetActivityId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest3.SetActivityId
---

# IWDFIoRequest3::SetActivityId


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The 
  <b>SetActivityId</b> method associates an activity identifier with an I/O request.

## -parameters

### -param ActivityId 

[in]
A pointer to the activity identifier GUID to store in the I/O request.

## -remarks

Calling <b>SetActivityId</b> does not set an association with any previously present activity identifier. When the driver calls <b>SetActivityId</b>, any existing activity identifier is overwritten.

To set an association, retrieve the existing identifier by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest3-retrieveactivityid">RetrieveActivityId</a> and then associate the existing identifier with the new one by calling <a href="https://docs.microsoft.com/windows/desktop/api/evntprov/nf-evntprov-eventwritetransfer">EventWriteTransfer</a>.

The framework does not clear a request's activity identifier when the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-reuse">IWdfIoRequest2::Reuse</a>.

For more information about activity identifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-activity-identifiers">Using Activity Identifiers</a>.

The UMDF 2 equivalent of this method is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetactivityid">WdfRequestSetActivityId</a>.


#### Examples

For a code example that uses <b>SetActivityId</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest3-retrieveactivityid">RetrieveActivityId</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest3">IWDFIoRequest3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest3-retrieveactivityid">IWDFIoRequest3::RetrieveActivityId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetactivityid">WdfRequestSetActivityId</a>

