---
UID: NC:ufxproprietarycharger.UFX_PROPRIETARY_CHARGER_DETECT
title: UFX_PROPRIETARY_CHARGER_DETECT (ufxproprietarycharger.h)
description: The filter driver's implementation to detect if a charger is attached and get details about the charger.
old-location: buses\ufx_proprietary_charger_detect.htm
tech.root: usbref
ms.assetid: E95D2713-8F95-460E-9107-4793B002A6AC
ms.date: 05/07/2018
keywords: ["UFX_PROPRIETARY_CHARGER_DETECT callback function"]
ms.keywords: PFN_UFX_PROPRIETARY_CHARGER_DETECT, PFN_UFX_PROPRIETARY_CHARGER_DETECT callback function pointer [Buses], UFX_PROPRIETARY_CHARGER_DETECT, UFX_PROPRIETARY_CHARGER_DETECT callback, UfxProprietaryChargerDetect, UfxProprietaryChargerDetect callback function [Buses], buses.ufx_proprietary_charger_detect, ufxproprietarycharger/UfxProprietaryChargerDetect
f1_keywords:
 - "ufxproprietarycharger/PFN_UFX_PROPRIETARY_CHARGER_DETECT"
 - "PFN_UFX_PROPRIETARY_CHARGER_DETECT"
req.header: ufxproprietarycharger.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ufxproprietarycharger.h
api_name:
- PFN_UFX_PROPRIETARY_CHARGER_DETECT
targetos: Windows
req.typenames: 
---

# UFX_PROPRIETARY_CHARGER_DETECT callback function


## -description


The filter driver's implementation to detect if a charger is attached  and get details about the charger.


## -parameters




### -param Context 
[in]
    A pointer to a driver-defined context.


### -param DetectedCharger 
[out]
A pointer to a     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxproprietarycharger/ns-ufxproprietarycharger-_ufx_proprietary_charger">UFX_PROPRIETARY_CHARGER</a> structure that the driver fills with charger information. 


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



To support handling of proprietary chargers, the USB lower filter driver must publish support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188012(v=vs.85)">USB filter driver for supporting proprietary chargers</a>.

In this callback function, the driver assigns the charger a GUID and sets the minimum required Dx state when the device is connected for charging. 


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
UsbLowerFilter_ProprietaryChargerDetect(
    __in PVOID Context,
    __out PUFX_PROPRIETARY_CHARGER DetectedCharger
    )
{
    NTSTATUS Status = STATUS_SUCCESS;

    PPDCP_CONTEXT PdcpContext = NULL;


    PAGED_CODE();

    PdcpContext = DeviceGetUsbLowerFilterContext((WDFDEVICE)Context);


    // Clear our event
     KeClearEvent(&PdcpContext>AbortOperation);


    // Wait for a while
     Timeout.QuadPart = WDF_REL_TIMEOUT_IN_MS(PdcpContext>DetectionDelayInms);

    Status = KeWaitForSingleObject(
        &PdcpContext>AbortOperation,
        Executive,
        KernelMode,
        FALSE,
        &Timeout);

    switch (Status)
    {
    case STATUS_SUCCESS:

        // The abort event was set. Abort.

        Status = STATUS_REQUEST_ABORTED;
        break;

    case STATUS_TIMEOUT:

        // Timed out, detection has completed successfully.
        // Check if we want to fail this.

        if (PdcpContext>RejectNextRequest)
        {
            PdcpContext->RejectNextRequest = FALSE;
            Status = STATUS_UNSUCCESSFUL;
        }
        else if (!PdcpContext->PdcpChargerAttached)
        {
            Status = STATUS_NOT_FOUND;
        }
        else
        {
            Status = STATUS_SUCCESS;
        }
        break;

    default:
        break;
    }

    if (NT_SUCCESS(Status))
    {
        PdcpContext->PdcpChargerDetected = TRUE;
        DetectedCharger->ChargerId = GUID_USBFN_PROPRIETARY_CHARGER;
        DetectedCharger->DxState = PowerDeviceD2;
    }

    return Status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188012(v=vs.85)">USB filter driver for supporting proprietary chargers</a>
 

 

