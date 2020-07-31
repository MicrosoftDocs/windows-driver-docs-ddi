---
UID: NF:wudfddi.IWDFIoTargetStateManagement.Start
title: IWDFIoTargetStateManagement::Start (wudfddi.h)
description: The Start method starts sending queued requests to a local I/O target.
old-location: wdf\iwdfiotargetstatemanagement_start.htm
tech.root: wdf
ms.assetid: e242b62a-7a4f-491b-b1a7-3388cf9c5a40
ms.date: 02/26/2018
keywords: ["IWDFIoTargetStateManagement::Start"]
ms.keywords: IWDFIoTargetStateManagement interface,Start method, IWDFIoTargetStateManagement.Start, IWDFIoTargetStateManagement::Start, Start, Start method, Start method,IWDFIoTargetStateManagement interface, UMDFIoTargetObjectRef_931a0267-704f-44f7-8f52-0344afb86f81.xml, umdf.iwdfiotargetstatemanagement_start, wdf.iwdfiotargetstatemanagement_start, wudfddi/IWDFIoTargetStateManagement::Start
f1_keywords:
 - "wudfddi/IWDFIoTargetStateManagement.Start"
 - "IWDFIoTargetStateManagement.Start"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFIoTargetStateManagement.Start
targetos: Windows
req.typenames: 
---

# IWDFIoTargetStateManagement::Start


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Start</b> method starts sending queued requests to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">local  I/O target</a>.


## -returns



<b>Start</b> returns S_OK if the operation succeeds. Otherwise, this method might return one of the error codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT (STATUS_INVALID_DEVICE_STATE)</b></dt>
</dl>
</td>
<td width="60%">
The device has been removed.

</td>
</tr>
</table>
 

This method might return one of the other error codes that Winerror.h defines.




## -remarks



If your driver can detect recoverable device errors, you might want your driver to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a> to temporarily stop sending requests to the local I/O target, then later call <b>Start</b> to resume sending requests.

Additionally, if a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetpipe2-configurecontinuousreader">IWDFUsbTargetPipe2::ConfigureContinuousReader</a> to configure a continuous reader for a USB pipe, the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0entry">IPnpCallback::OnD0Entry</a> callback function must call <b>Start</b> to start the reader.

Your driver must call <b>Start</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotargetstatemanagement-stop">IWDFIoTargetStateManagement::Stop</a> synchronously. After the driver calls one of these functions, it must not call the other function before the first one returns.

For more information about <b>Start</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state-in-umdf">Controlling a General I/O Target's State in UMDF</a>. 

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets-in-umdf">Using I/O Targets in UMDF</a>. 


#### Examples

The following code example first shows how a driver can obtain the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiotargetstatemanagement">IWDFIoTargetStateManagement</a> interface for a USB pipe object. The code example then  shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0entry">IPnpCallback::OnD0Entry</a> callback function can call <b>Start</b>, if the driver uses a continuous reader for the USB pipe. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
    IWDFIoTargetStateManagement * m_pIoTargetInterruptPipeStateMgmt = NULL;

    IWDFUsbTargetFactory *  pIUsbTargetFactory = NULL;
    IWDFUsbTargetDevice *   pIUsbTargetDevice = NULL;
    IWDFUsbInterface *      pIUsbInterface = NULL;
    IWDFUsbTargetPipe *     pIUsbPipe = NULL;

    hr = m_FxDevice->QueryInterface(IID_PPV_ARGS(&pIUsbTargetFactory));
    if (FAILED(hr))
    {...}
    hr = pIUsbTargetFactory->CreateUsbTargetDevice(&pIUsbTargetDevice);
    if (FAILED(hr))
    {...}
    hr = pIUsbTargetDevice->RetrieveUsbInterface(0, &pIUsbInterface);
    if (FAILED(hr))
    {...}
    NumEndPoints = pIUsbInterface->GetNumEndPoints();
    for (UCHAR PipeIndex = 0; PipeIndex < NumEndPoints; PipeIndex++)
    {
        hr = pIUsbInterface->RetrieveUsbPipeObject(PipeIndex, &pIUsbPipe);
        if (FAILED(hr))
        {...}
        else
        {
            if (pIUsbPipe->IsInEndPoint())
            {
                if (UsbdPipeTypeInterrupt == pIUsbPipe->GetType())
                {
                    m_pIUsbInterruptPipe = pIUsbPipe;
                    hr = m_pIUsbInterruptPipe->QueryInterface(IID_PPV_ARGS(&m_pIoTargetInterruptPipeStateMgmt));
                    if (FAILED(hr))
                    {...}
                }
            }
        }
    } 

HRESULT
CMyDevice::OnD0Entry(
    __in IWDFDevice*  pWdfDevice,
    __in WDF_POWER_DEVICE_STATE  previousState
    )
{
...
    m_pIoTargetInterruptPipeStateMgmt->Start();
...
    return S_OK;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiotargetstatemanagement">IWDFIoTargetStateManagement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-stop">IWDFRemoteTarget::Stop</a>
 

 

