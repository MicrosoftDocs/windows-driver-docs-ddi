---
UID: NF:portcls.PcNewMiniport
title: PcNewMiniport function
author: windows-driver-content
description: The PcNewMiniport function creates an instance of one of the system-supplied miniport drivers that are built into the PortCls system driver, portcls.sys.
old-location: audio\pcnewminiport.htm
old-project: audio
ms.assetid: 15046dc7-42ae-4ebe-acb9-2b0bbad1e833
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.pcnewminiport, portcls/PcNewMiniport, PcNewMiniport function [Audio Devices], audpc-routines_d0b1d8e9-e4e0-44de-8854-a1b18eac9ff5.xml, PcNewMiniport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcNewMiniport function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Portcls.lib
-	Portcls.dll
apiname:
-	PcNewMiniport
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# PcNewMiniport function


## -description


The <b>PcNewMiniport</b> function creates an instance of one of the system-supplied miniport drivers that are built into the PortCls system driver, portcls.sys. A class ID specifies which of these miniport drivers to instantiate. The driver supports a miniport interface that is derived from <a href="..\portcls\nn-portcls-iminiport.md">IMiniport</a>.


## -syntax


````
NTSTATUS PcNewMiniport(
  _Out_ PMINIPORT *OutMiniport,
  _In_  REFCLSID  ClassId
);
````


## -parameters




### -param OutMiniPort

TBD


### -param ClassID

TBD




#### - ClassId [in]

Specifies the miniport interface that is being requested. For more information, see the following Remarks section.


#### - OutMiniport [out]

Output pointer for the miniport-driver object created by this function. This parameter points to a caller-allocated pointer variable into which the function outputs a reference to the newly created <a href="..\portcls\nn-portcls-iminiport.md">IMiniport</a> object. This object is an instance of the miniport driver that is specified by the <i>ClassId</i> parameter. Specify a valid, non-NULL pointer value for this parameter.


## -returns



<b>PcNewMiniport</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



The system-supplied miniport drivers for MPU-401 UARTs and OPL3 synthesizers can be instantiated by calling <b>PcNewMiniport</b> These are built-in miniport drivers that are provided with the portcls.sys system driver. Miniport drivers that are part of a vendor's adapter driver are not created in this way.

The <i>ClassId</i> parameter can be set to one of the GUIDs in the following table.

<table>
<tr>
<th>GUID</th>
<th>System-Supplied Driver</th>
</tr>
<tr>
<td>
<b>CLSID_MiniportDriverDMusUART</b>

</td>
<td>
DMusUART miniport driver for MPU-401 synth device. Exposes <a href="..\dmusicks\nn-dmusicks-iminiportdmus.md">IMiniportDMus</a> interface for use with <a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a> port object.

</td>
</tr>
<tr>
<td>
<b>CLSID_MiniportDriverDMusUARTCapture</b>

</td>
<td>
DMusUARTCapture miniport driver for MPU-401 capture device. Exposes <a href="..\dmusicks\nn-dmusicks-iminiportdmus.md">IMiniportDMus</a> interface for use with <a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a> port object.

</td>
</tr>
<tr>
<td>
<b>CLSID_MiniportDriverFmSynth</b>

</td>
<td>
FmSynth miniport driver for FM synth device. Exposes <a href="..\portcls\nn-portcls-iminiportmidi.md">IMiniportMidi</a> interface for use with <a href="..\portcls\nn-portcls-iportmidi.md">IPortMidi</a> port object.

</td>
</tr>
<tr>
<td>
<b>CLSID_MiniportDriverFmSynthWithVol</b>

</td>
<td>
Same as the preceding entry, except that the driver also supports a volume node.

</td>
</tr>
<tr>
<td>
<b>CLSID_MiniportDriverUart</b>

</td>
<td>
UART miniport driver for MPU-401 synth device. Exposes <a href="..\portcls\nn-portcls-iminiportmidi.md">IMiniportMidi</a> interface for use with <a href="..\portcls\nn-portcls-iportmidi.md">IPortMidi</a> port object. Obsolete.

</td>
</tr>
</table>
 

The first two GUIDs in the preceding table are defined in header file dmusicks.h; the last three are defined in portcls.h.

The DMusUART miniport driver outputs MIDI data to a synth device with a pure MPU-401 MIDI interface. To produce sound, this device needs an external MIDI sound module attached to it.

The DMusUARTCapture miniport driver inputs MIDI data from a capture device with a pure MPU-401 interface.

The FMSynth miniport driver outputs MIDI data to a synth device that implements OPL3-style FM synthesis. The <b>CLSID_MiniportDriverFmSynth</b> GUID is appropriate for most FM synth devices. However, devices such as the Windows Sound System that do not provide a hardware volume control after the FM synth should use the <b>CLSID_MiniportDriverFmSynthWithVol</b> GUID instead. In Windows Server SP1 and later, the FMSynth miniport driver is available only in 32-bit versions of the operating system.

The UART miniport driver is obsolete. New adapter driver code should use the DMusUART miniport driver, which supersedes UART and implements a superset of its functionality.

Microsoft provides the source code for the DMusUART and FMSynth miniport drivers, which can serve as a starting point for hardware vendors who might need to extend these drivers to manage additional device capabilities. Look in the sample audio drivers in the Windows Driver Kit (WDK).

See <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a> For more information about creating port and miniport drivers for subdevices.

The <i>OutMiniport</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also

<a href="..\portcls\nn-portcls-iminiport.md">IMiniport</a>



<a href="..\portcls\nn-portcls-iportmidi.md">IPortMidi</a>



<a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a>



<a href="..\dmusicks\nn-dmusicks-iminiportdmus.md">IMiniportDMus</a>



<a href="..\portcls\nn-portcls-iminiportmidi.md">IMiniportMidi</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcNewMiniport function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

