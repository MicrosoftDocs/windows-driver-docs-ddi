---
UID: NI:gnssdriver.IOCTL_GNSS_RESPOND_NI
title: IOCTL_GNSS_RESPOND_NI (gnssdriver.h)
description: The IOCTL_GNSS_RESPOND_NI control code is used by the GNSS adapter to respond to an NI request that was asynchronously communicated to it by the GNSS driver through the resolution of an IOCTL_GNSS_LISTEN_NI request.
old-location: gnss\ioctl_gnss_respond_ni.htm
tech.root: gnss
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_RESPOND_NI IOCTL"]
ms.keywords: IOCTL_GNSS_RESPOND_NI, IOCTL_GNSS_RESPOND_NI control, IOCTL_GNSS_RESPOND_NI control code [Sensor Devices], gnss.ioctl_gnss_respond_ni, gnssdriver/IOCTL_GNSS_RESPOND_NI
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_GNSS_RESPOND_NI
 - gnssdriver/IOCTL_GNSS_RESPOND_NI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - IOCTL_GNSS_RESPOND_NI
---

# IOCTL_GNSS_RESPOND_NI IOCTL


## -description

The <b>IOCTL_GNSS_RESPOND_NI</b> control code is used by the GNSS adapter to respond to an NI request that was asynchronously communicated to it by the GNSS driver through the resolution of an <a href="/windows-hardware/drivers/ddi/gnssdriver/ni-gnssdriver-ioctl_gnss_listen_ni">IOCTL_GNSS_LISTEN_NI</a> request.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

A pointer to a <a href="/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_ni_response">GNSS_NI_RESPONSE</a> structure.

### -input-buffer-length

Set to sizeof(GNSS_NI_RESPONSE).

### -output-buffer

Set to NULL.

### -output-buffer-length

Set to 0.

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

## -remarks

The driver sets one of the following NTSTATUS values to indicate result.

<ul>
<li>
<b>STATUS_SUCCESS</b>, when the driver processed the users NI response information successfully.

</li>
<li>
<b>Failed</b>, when the driver does not process the users NI response information successfully.

</li>
<li>
<b>Ignored</b>, when the driver ignored the users NI response information.



</li>
</ul>
<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
It is the GNSS driver’s responsibility to pass the user’s response, contained in the <b>GNSS_NI_RESPONSE</b> input structure to the NI. If the response is <b>GNSS_Ni_UserResponseTimeout</b>, the driver should determine the appropriate default response after time-out and send it to the SUPL server.

## -see-also

<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
