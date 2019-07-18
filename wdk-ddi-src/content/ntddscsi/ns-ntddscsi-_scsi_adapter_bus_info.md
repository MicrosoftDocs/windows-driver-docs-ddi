---
UID: NS:ntddscsi._SCSI_ADAPTER_BUS_INFO
title: _SCSI_ADAPTER_BUS_INFO (ntddscsi.h)
description: The SCSI_ADAPTER_BUS_INFO structure is used in conjunction with the IOCTL_SCSI_GET_INQUIRY_DATA request to retrieve the SCSI inquiry data for all devices on a given SCSI bus.
old-location: storage\scsi_adapter_bus_info.htm
tech.root: storage
ms.assetid: 786d6813-a9f3-437e-9b41-d69e0fce9a4c
ms.date: 03/29/2018
ms.keywords: "*PSCSI_ADAPTER_BUS_INFO, PSCSI_ADAPTER_BUS_INFO, PSCSI_ADAPTER_BUS_INFO structure pointer [Storage Devices], SCSI_ADAPTER_BUS_INFO, SCSI_ADAPTER_BUS_INFO structure [Storage Devices], _SCSI_ADAPTER_BUS_INFO, ntddscsi/PSCSI_ADAPTER_BUS_INFO, ntddscsi/SCSI_ADAPTER_BUS_INFO, storage.scsi_adapter_bus_info, structs-scsibus_f21bd933-bcbc-48b5-8904-845712ce226f.xml"
ms.topic: struct
f1_keywords:
 - "ntddscsi/SCSI_ADAPTER_BUS_INFO"
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddscsi.h
api_name:
- SCSI_ADAPTER_BUS_INFO
product:
- Windows
targetos: Windows
req.typenames: SCSI_ADAPTER_BUS_INFO, *PSCSI_ADAPTER_BUS_INFO
---

# _SCSI_ADAPTER_BUS_INFO structure


## -description


The SCSI_ADAPTER_BUS_INFO structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ni-ntddscsi-ioctl_scsi_get_inquiry_data">IOCTL_SCSI_GET_INQUIRY_DATA</a> request to retrieve the SCSI inquiry data for all devices on a given SCSI bus. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field NumberOfBuses

Contains the number of buses on the adapter for which inquiry data is being reported. 


### -field BusData

Contains a variable length array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_bus_data">SCSI_BUS_DATA</a> structures that hold the inquiry data. 


## -remarks



SCSI_ADAPTER_BUS_INFO is a header structure that describes the layout of the output buffer of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ni-ntddscsi-ioctl_scsi_get_inquiry_data">IOCTL_SCSI_GET_INQUIRY_DATA</a> request. This request returns SCSI inquiry data for all of the logical units on all of the buses associated with a particular SCSI host bus adapter (HBA). The <b>BusData</b> member of SCSI_ADAPTER_BUS_INFO contains a variable length array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_bus_data">SCSI_BUS_DATA</a> structures. This array has one element for each SCSI bus on the adapter, so its size is equal to the number of buses indicated in the <b>NumberOfBuses</b> member of SCSI_ADAPTER_BUS_INFO. 

In most cases, <b>NumberOfBuses</b> will have a value of 1. Early SCSI buses were limited to 36 targets (rather than the current limit of 128), so some vendors manufactured HBAs with several buses, in order to increase the maximum number of targets. To support these older HBAs, Windows provides a mechanism for retrieving inquiry data from HBAs with multiple buses. For adapters with a single bus, <b>NumberOfBuses</b> will be one, and the <b>BusData</b> member of SCSI_ADAPTER_BUS_INFO will have only one element, but HBAs with multiple buses will generate data for multiple SCSI_BUS_DATA structures, and <b>NumberOfBuses</b> will be greater than 1.

Immediately following the array in <b>BusData</b> is the inquiry data for all of the devices on all the buses that belong to the HBA. The <b>InquiryDataOffset</b> member of each SCSI_BUS_DATA structure provides an offset to the inquiry data for the corresponding SCSI bus. 

The inquiry data for each SCSI bus includes information about all of the logical units on that bus. Each logical unit's inquiry data is formatted in a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_inquiry_data">SCSI_INQUIRY_DATA</a>, and all of the SCSI_INQUIRY_DATA structures for a particular bus are linked together by the <b>NextInquiryDataOffset</b> member. There will be a separate list for each SCSI bus, and the <b>NextInquiryDataOffset</b> member of the last structure in each list contains a value of zero. 

The following pseudocode example illustrates how to step through the SCSI buses on an HBA, and the logical units for each bus, reading and printing the inquiry data for each logical unit:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
PrintInquiryData(PCHAR  DataBuffer)
{
    PSCSI_ADAPTER_BUS_INFO  adapterInfo;
    PSCSI_INQUIRY_DATA inquiryData;
    ULONG i, j;

    adapterInfo = (PSCSI_ADAPTER_BUS_INFO) DataBuffer;
    for (i = 0; i < adapterInfo->NumberOfBuses; i++) {
       inquiryData = (PSCSI_INQUIRY_DATA) (DataBuffer +
          adapterInfo->BusData[i].InquiryDataOffset);
       while (adapterInfo->BusData[i].InquiryDataOffset) {
          printf(" %d   %d  %3d    %s    %.28s ",
             i,
             inquiryData->TargetId,
             inquiryData->Lun,
             (inquiryData->DeviceClaimed) ? "Y" : "N",
             &inquiryData->InquiryData[8]);
          for (j = 0; j < 8; j++) {
             printf("%02X ", inquiryData->InquiryData[j]);
          }
          printf("\n");
          if (inquiryData->NextInquiryDataOffset == 0) {
             break;
          }
          inquiryData = (PSCSI_INQUIRY_DATA) (DataBuffer +
             inquiryData->NextInquiryDataOffset);
       }
    }
    printf("\n\n");
}</pre>
</td>
</tr>
</table></span></div>
You must use <b>NextInquiryDataOffset</b> member to locate the inquiry data for next logical unit. Do not try to do this by pointer arithmetic. The positioning of each SCSI_INQUIRY_DATA structure is potentially different for each HBA miniport driver, because it depends on data alignment requirements.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ni-ntddscsi-ioctl_scsi_get_inquiry_data">IOCTL_SCSI_GET_INQUIRY_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_bus_data">SCSI_BUS_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddscsi/ns-ntddscsi-_scsi_inquiry_data">SCSI_INQUIRY_DATA</a>
 

 

