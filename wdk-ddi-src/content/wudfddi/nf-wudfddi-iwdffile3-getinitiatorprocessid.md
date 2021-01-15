---
UID: NF:wudfddi.IWDFFile3.GetInitiatorProcessId
title: IWDFFile3::GetInitiatorProcessId (wudfddi.h)
description: The GetInitiatorProcessId method retrieves the initiator process ID associated with an IWDFFile interface.
old-location: wdf\iwdffile3_getinitiatorprocessid.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFFile3::GetInitiatorProcessId"]
ms.keywords: GetInitiatorProcessId, GetInitiatorProcessId method, GetInitiatorProcessId method,IWDFFile3 interface, IWDFFile3 interface,GetInitiatorProcessId method, IWDFFile3.GetInitiatorProcessId, IWDFFile3::GetInitiatorProcessId, umdf.iwdffile3_getinitiatorprocessid, wdf.iwdffile3_getinitiatorprocessid, wudfddi/IWDFFile3::GetInitiatorProcessId
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFFile3::GetInitiatorProcessId
 - wudfddi/IWDFFile3::GetInitiatorProcessId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFFile3::GetInitiatorProcessId
---

# IWDFFile3::GetInitiatorProcessId


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInitiatorProcessId</b> method retrieves the initiator process ID associated with an <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface.

## -parameters

### -param pdwProcessId 

[out]
Specifies the address of a location that receives the initiator process identifier associated with the file, if any exists.  Otherwise, the location receives 0.

## -remarks

Starting in Windows 8, a system component may issue a create on behalf of an app. The driver can call <b>GetInitiatorProcessId</b> to determine which process the create operation is ultimately intended for.

<b>GetInitiatorProcessId</b> returns zero if no initiator process is associated with the create operation.

For more information about framework file objects, see <a href="/windows-hardware/drivers/wdf/driver-created-versus-application-created-file-objects">Driver-Created Versus Application-Created File Objects</a>.


#### Examples


```
VOID
STDMETHODCALLTYPE
CMyQueue::OnCreateFile(
    __in IWDFIoQueue *pWdfQueue,
    __in IWDFIoRequest *pWdfRequest,
    __in IWDFFile*  pWdfFileObject
    )
 ...
    IWDFFile3*  pWdfFileObject3 = NULL;
    HRESULT  hr = S_OK;
    DWORD initiatorProcessId;

    //
    // Obtain IWDFFile3 interface from IWDFFile.
    //
    hr = pWdfFileObject->QueryInterface(IID_PPV_ARGS(&pWdfFileObject3));
    if (!SUCCEEDED(hr))
    {
        goto Done;
    }
    pWdfFileObject3->GetInitiatorProcessId(&initiatorProcessId);
    ...


```

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile3">IWDFFile3</a>

