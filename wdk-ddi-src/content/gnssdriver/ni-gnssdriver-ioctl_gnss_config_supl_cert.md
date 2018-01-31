---
UID: NI:gnssdriver.IOCTL_GNSS_CONFIG_SUPL_CERT
title: IOCTL_GNSS_CONFIG_SUPL_CERT
author: windows-driver-content
description: The IOCTL_GNSS_CONFIG_SUPL_CERT control code is used by the GNSS adapter to set SUPL certificates.
old-location: sensors\ioctl_gnss_config_supl_cert.htm
old-project: sensors
ms.assetid: 34095934-26C1-4855-9ED9-71627E88A903
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: sensors.ioctl_gnss_config_supl_cert, IOCTL_GNSS_CONFIG_SUPL_CERT control code [Sensor Devices], IOCTL_GNSS_CONFIG_SUPL_CERT, gnssdriver/IOCTL_GNSS_CONFIG_SUPL_CERT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	IOCTL_GNSS_CONFIG_SUPL_CERT
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_CONFIG_SUPL_CERT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_GNSS_CONFIG_SUPL_CERT</b> control code is used by the GNSS adapter to set SUPL certificates.


## -ioctlparameters




### -input-buffer

Pointer to a <a href="..\gnssdriver\ns-gnssdriver-gnss_supl_cert_config.md">GNSS_SUPL_CERT_CONFIG</a> structure.


### -input-buffer-length

Set to sizeof(<b>GNSS_SUPL_CERT_CONFIG</b>).


### -output-buffer

Set to <b>NULL</b>.


### -output-buffer-length

Set to 0.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks


The driver sets one of the following NTSTATUS values to indicate result.
<ul>
<li>
STATUS_SUCCESS, when the driver processes the SUPL certificate information successfully. If the IOCTL tries to delete or purge certificates that don’t exist, it still returns STATUS_SUCCESS.

</li>
<li>
Failed, when the driver does not process the SUPL certificate information successfully.

</li>
<li>
Ignored, when the driver ignores the SUPL certificate information.

</li>
</ul><h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>For GNSS DDI version 1:

The GNSS adapter does not  need to do anything special.

For GNSS DDI version 2 and later:

The GNSS adapter will only refer to certificates by name. It will be up to the GNSS driver to map the certificate names internally to any other representation or reference to the certificates, if needed.

The GNSS adapter will do a full purge or all previously injected certificates if needed before injecting a new set.
<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>The GNSS driver needs to pass this certificate information to the SUPL component which should use the certificate to set up secure connection with H-SLP.

For GNSS DDI version 2 and later:

The GNSS driver must support receiving multiple calls of the <b>IOCTL_GNSS_CONFIG_SUPL_CERT</b>. The GNSS adapter will call this IOCTL multiple times, each time to inject a different root certificate. Different root certificates are identified by having a different <b>SuplCertName</b>, which provides the name of the certificate being injected.
<ul>
<li>
If the name is the same as a previously configured certificate, then the certificate will be replaced.

</li>
<li>
If the name is different from certificate, then the new certificate will be added.

</li>
</ul>If a certificate with the same name as an existing certificate is injected again, the GNSS driver should overwrite the previous certificate with the same name.



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_CONFIG_SUPL_CERT control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

