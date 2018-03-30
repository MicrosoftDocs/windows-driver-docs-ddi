---
UID: NA:hbaapi
ms.assetid: f9f421a5-4a0e-36cc-9ce6-0dca2fee93c8
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Hbaapi.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Hbaapi.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [HBA_CloseAdapter function](nf-hbaapi-hba_closeadapter.md) | The HBA_CloseAdapter routine releases system resources associated with the indicated open HBA handle. |
| [HBA_FreeLibrary function](nf-hbaapi-hba_freelibrary.md) | The HBA_FreeLibrary routine releases system resources associated with fibre channel HBA library. |
| [HBA_GetAdapterAttributes function](nf-hbaapi-hba_getadapterattributes.md) | The HBA_GetAdapterAttributes routine retrieves the attributes for an HBA. |
| [HBA_GetAdapterName function](nf-hbaapi-hba_getadaptername.md) | The HBA_GetAdapterName routine retrieves the text string that identifies the HBA name that corresponds to the indicated adapter index. |
| [HBA_GetAdapterPortAttributes function](nf-hbaapi-hba_getadapterportattributes.md) | The HBA_GetAdapterPortAttributes routine retrieves the attributes for a specified remote fibre channel port. |
| [HBA_GetBindingCapability function](nf-hbaapi-hba_getbindingcapability.md) | The HBA_GetBindingCapability routine retrieves the binding capabilities of the indicated port. |
| [HBA_GetBindingSupport function](nf-hbaapi-hba_getbindingsupport.md) | The HBA_GetBindingSupport routine retrieves the binding capabilities currently enabled for the specified port. |
| [HBA_GetDiscoveredPortAttributes function](nf-hbaapi-hba_getdiscoveredportattributes.md) | The HBA_GetDiscoveredPortAttributes routine retrieves the attributes for a specified remote fibre channel port. |
| [HBA_GetEventBuffer function](nf-hbaapi-hba_geteventbuffer.md) | The HBA_GetEventBuffer routine retrieves the indicated number of events, if available, from the HBA's event queue. |
| [HBA_GetFC4Statistics function](nf-hbaapi-hba_getfc4statistics.md) | The HBA_GetFC4Statistics routine retrieves traffic statistics that a specific FC-4 protocol has collected for the indicated port and local adapter. |
| [HBA_GetFCPStatistics function](nf-hbaapi-hba_getfcpstatistics.md) | The HBA_GetFCPStatistics routine retrieves traffic statistics that the fibre channel protocol (FCP) has collected for the indicated logical unit. |
| [HBA_GetFcpPersistentBinding function](nf-hbaapi-hba_getfcppersistentbinding.md) | The HBA_GetFcpPersistentBinding routine retrieves the persistent bindings that are associated with the logical units that the HBA can enumerate. |
| [HBA_GetFcpTargetMapping function](nf-hbaapi-hba_getfcptargetmapping.md) | The HBA_GetFcpTargetMapping routine retrieves the mappings between operating system and fibre channel protocol (FCP) identifiers for a set of targets that the HBA can enumerate. |
| [HBA_GetFcpTargetMappingV2 function](nf-hbaapi-hba_getfcptargetmappingv2.md) | The HBA_GetFcpTargetMappingV2 routine retrieves the mappings between operating system and fibre channel protocol (FCP) identifiers for a set of targets that the HBA can enumerate on the indicated port. |
| [HBA_GetNumberOfAdapters function](nf-hbaapi-hba_getnumberofadapters.md) | The HBA_GetNumberOfAdapters routine returns the number of HBAs supported by the library. |
| [HBA_GetPersistentBindingV2 function](nf-hbaapi-hba_getpersistentbindingv2.md) | The HBA_GetPersistentBindingV2 routine retrieves persistent bindings, including extended bindings, for logical units that the HBA enumerates on the indicated port. |
| [HBA_GetPortAttributesByWWN function](nf-hbaapi-hba_getportattributesbywwn.md) | The HBA_GetPortAttributesByWWN routine retrieves the attributes for the port specified by the indicated port name. |
| [HBA_GetPortStatistics function](nf-hbaapi-hba_getportstatistics.md) | The HBA_GetPortStatistics routine retrieves statistics for the indicated port on the HBA. |
| [HBA_GetRNIDMgmtInfo function](nf-hbaapi-hba_getrnidmgmtinfo.md) | The HBA_GetRNIDMgmtInfo routine queries the HBA for request node identification data (RNID) management information. |
| [HBA_GetVendorLibraryAttributes function](nf-hbaapi-hba_getvendorlibraryattributes.md) | The HBA_GetVendorLibraryAttributes routine retrieves the vendor-specific attributes of the fibre channel HBA API library. |
| [HBA_GetVersion function](nf-hbaapi-hba_getversion.md) | The HBA_GetVersion routine returns the version of the fibre channel HBA API specification with which the HBA API library is compatible. |
| [HBA_GetWrapperLibraryAttributes function](nf-hbaapi-hba_getwrapperlibraryattributes.md) | The HBA_GetWrapperLibraryAttributes routine retrieves the attributes of the fibre channel HBA API library that are operating system-specific. |
| [HBA_LoadLibrary function](nf-hbaapi-hba_loadlibrary.md) | The HBA_LoadLibrary routine loads and initializes the system-supplied fibre channel HBA API library. |
| [HBA_OpenAdapter function](nf-hbaapi-hba_openadapter.md) | The HBA_OpenAdapter routine opens an HBA and returns a handle. |
| [HBA_OpenAdapterByWWN function](nf-hbaapi-hba_openadapterbywwn.md) | The HBA_OpenAdapterByWWN routine opens the HBA that is associated with either a node or a port that has the indicated name. |
| [HBA_RefreshAdapterConfiguration function](nf-hbaapi-hba_refreshadapterconfiguration.md) | The HBA_RefreshAdapterConfiguration routine refreshes the library's internally cached HBA data. |
| [HBA_RefreshInformation function](nf-hbaapi-hba_refreshinformation.md) | The HBA_RefreshInformation routine refreshes the library's internally cached data for the indicated HBA. |
| [HBA_RegisterForAdapterAddEvents function](nf-hbaapi-hba_registerforadapteraddevents.md) | The HBA_RegisterForAdapterAddEvents routine registers the indicated user callback routine to call when a new adapter is added to the system. |
| [HBA_RegisterForAdapterEvents function](nf-hbaapi-hba_registerforadapterevents.md) | The HBA_RegisterForAdapterEvents routine registers the indicated user callback routine to call when an adapter event occurs. |
| [HBA_RegisterForAdapterPortEvents function](nf-hbaapi-hba_registerforadapterportevents.md) | The HBA_RegisterForAdapterPortEvents routine registers the indicated user callback routine to call when a port event occurs. |
| [HBA_RegisterForAdapterPortStatEvents function](nf-hbaapi-hba_registerforadapterportstatevents.md) | The HBA_RegisterForAdapterPortStatEvents routine registers the indicated user callback routine to call when a port statistics event occurs. |
| [HBA_RegisterForLinkEvents function](nf-hbaapi-hba_registerforlinkevents.md) | The HBA_RegisterForLinkEvents routine registers with a specified adapter for asynchronous fabric link-level events. |
| [HBA_RegisterForTargetEvents function](nf-hbaapi-hba_registerfortargetevents.md) | The HBA_RegisterForTargetEvents routine registers for target events with a specified target or with all targets associated with an adapter. |
| [HBA_RegisterLibrary function](nf-hbaapi-hba_registerlibrary.md) | "." |
| [HBA_RegisterLibraryV2 function](nf-hbaapi-hba_registerlibraryv2.md) | "." |
| [HBA_RemoveAllPersistentBindings function](nf-hbaapi-hba_removeallpersistentbindings.md) | The HBA_RemoveAllPersistentBindings routine removes all persistent bindings for a specified HBA port. |
| [HBA_RemoveCallback function](nf-hbaapi-hba_removecallback.md) | The HBA_RemoveCallback routine de-registers a callback routine. |
| [HBA_RemovePersistentBinding function](nf-hbaapi-hba_removepersistentbinding.md) | The HBA_RemovePersistentBinding routine retrieves information about the specified target. |
| [HBA_ResetStatistics function](nf-hbaapi-hba_resetstatistics.md) | The HBA_ResetStatistics routine resets the statistics counters for the indicated port and HBA. |
| [HBA_ScsiInquiryV2 function](nf-hbaapi-hba_scsiinquiryv2.md) | The HBA_ScsiInquiryV2 routine sends a SCSI inquiry command to the specified remote port. |
| [HBA_ScsiReadCapacityV2 function](nf-hbaapi-hba_scsireadcapacityv2.md) | The HBA_ScsiReadCapacityV2 routine sends a SCSI read capacity command to the indicated remote port. |
| [HBA_ScsiReportLUNsV2 function](nf-hbaapi-hba_scsireportlunsv2.md) | The HBA_ScsiReportLUNsV2 routine sends a SCSI report LUNs command to the indicated remote port. |
| [HBA_SendCTPassThru function](nf-hbaapi-hba_sendctpassthru.md) | The HBA_SendCTPassThru routine sends a common transport (CT) pass-through command. |
| [HBA_SendCTPassThruV2 function](nf-hbaapi-hba_sendctpassthruv2.md) | The HBA_SendCTPassThruV2 routine sends a common transport (CT) pass-through command through the indicated port. |
| [HBA_SendLIRR function](nf-hbaapi-hba_sendlirr.md) | The HBA_SendLIRR routine registers or de-registers a local (source) port to receive link incident records (LIR) from a remote (destination) port. |
| [HBA_SendRLS function](nf-hbaapi-hba_sendrls.md) | The HBA_SendRLS WMI routine sends a read link error status block (RLS) request through the indicated local port to the indicated remote port to retrieve a link error status block associated with the remote port. |
| [HBA_SendRNID function](nf-hbaapi-hba_sendrnid.md) | The HBA_SendRNID routine sends a request for node identification data (RNID) to the indicated HBA, which in turn routes the request through the indicated port or node to the appropriate fabric configuration server. |
| [HBA_SendRNIDV2 function](nf-hbaapi-hba_sendrnidv2.md) | The HBA_SendRNIDV2 routine sends a request for node identification data (RNID) to the indicated HBA, which in turn routes the request through the indicated port or node to the appropriate fabric configuration server. |
| [HBA_SendRPL function](nf-hbaapi-hba_sendrpl.md) | The HBA_SendRPL routine sends a read port list (RPL) request to the indicated port or domain controller. |
| [HBA_SendRPS function](nf-hbaapi-hba_sendrps.md) | The HBA_SendRPS routine sends a read port status block (RPS) request to the indicated agent port or domain controller. |
| [HBA_SendReadCapacity function](nf-hbaapi-hba_sendreadcapacity.md) | The HBA_SendReadCapacity routine sends a SCSI read capacity command to the indicated remote port. |
| [HBA_SendReportLUNs function](nf-hbaapi-hba_sendreportluns.md) | The HBA_SendReportLUNs routine sends a SCSI report LUNs command to the indicated remote port. |
| [HBA_SendSRL function](nf-hbaapi-hba_sendsrl.md) | The HBA_SendSRL routine issues a scan remote loop (SRL) request through the specified HBA to a specified domain controller. |
| [HBA_SendScsiInquiry function](nf-hbaapi-hba_sendscsiinquiry.md) | The HBA_SendScsiInquiry routine sends a SCSI inquiry command to the indicated remote port. |
| [HBA_SetBindingSupport function](nf-hbaapi-hba_setbindingsupport.md) | The HBA_SetBindingSupport routine enables the indicated set of capabilities on the adapter. |
| [HBA_SetPersistentBindingV2 function](nf-hbaapi-hba_setpersistentbindingv2.md) | The HBA_SetPersistentBindingV2 routine establishes a set of bindings between operating system and fibre channel protocol (FCP) identifiers for the logical units that the HBA can enumerate on the specified port. |
| [HBA_SetRNIDMgmtInfo function](nf-hbaapi-hba_setrnidmgmtinfo.md) | The HBA_SetRNIDMgmtInfo routine programs the HBA to return the indicated request node identification information data (RNID). |

## Structures

| Title   | Description   |
| ---- |:---- |
| [HBA_AdapterAttributes structure](ns-hbaapi-hba_adapterattributes.md) | The HBA_AdapterAttributes structure is used in conjunction with the HBA_GetAdapterAttributes routine to report the attributes of an HBA. |
| [HBA_EventInfo structure](ns-hbaapi-hba_eventinfo.md) | The HBA_EventInfo structure contains information about an event of the indicated type. |
| [HBA_FC4Statistics structure](ns-hbaapi-hba_fc4statistics.md) | The HBA_FC4Statistics structure contains port statistics. |
| [HBA_FCPBinding structure](ns-hbaapi-hba_fcpbinding.md) | The HBA_FCPBinding structure contains an array of bindings between operating system and fibre channel protocol (FCP) identifiers for a set of logical units. |
| [HBA_FCPBinding2 structure](ns-hbaapi-hba_fcpbinding2.md) | The HBA_FCPBinding2 structure contains an array of bindings between operating system identifiers, SCSI logical unit ID descriptors (LUIDs) and fibre channel protocol (FCP) identifiers for a set of logical units. |
| [HBA_FCPBindingEntry structure](ns-hbaapi-hba_fcpbindingentry.md) | The HBA_FCPBindingEntry structure is equivalent to HBAFCPBindingEntry. |
| [HBA_FCPBindingEntry2 structure](ns-hbaapi-hba_fcpbindingentry2.md) | The HBA_FCPBindingEntry2 structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit. |
| [HBA_FCPTargetMapping structure](ns-hbaapi-hba_fcptargetmapping.md) | The HBA_FCPTargetMapping structure contains an array of bindings between operating system and fibre channel protocol (FCP) identifiers for a set of target devices. |
| [HBA_FCPTargetMappingV2 structure](ns-hbaapi-hba_fcptargetmappingv2.md) | The HBA_FCPTargetMappingV2 structure contains a variable length array of target mappings. |
| [HBA_FcpId structure](ns-hbaapi-hba_fcpid.md) | The HBA_FcpId structure is identical to the HBAFCPID structure. |
| [HBA_FcpScsiEntry structure](ns-hbaapi-hba_fcpscsientry.md) | The HBA_FcpScsiEntry structure defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit. |
| [HBA_FcpScsiEntryV2 structure](ns-hbaapi-hba_fcpscsientryv2.md) | The HBA_FcpScsiEntryV2 structure defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit. |
| [HBA_LUID structure](ns-hbaapi-hba_luid.md) | The HBA_LUID structure contains the identification descriptor from the device identification page of the vital products data returned by a SCSI INQUIRY command. |
| [HBA_LibraryAttributes structure](ns-hbaapi-hba_libraryattributes.md) | The HBA_LibraryAttributes structure holds the library attributes. |
| [HBA_Link_EventInfo structure](ns-hbaapi-hba_link_eventinfo.md) | The HBA_Link_EventInfo structure contains information about a WMI link event associated with the fibre channel HBA API. |
| [HBA_MgmtInfo structure](ns-hbaapi-hba_mgmtinfo.md) | The HBA_MgmtInfo structure is used in conjunction with the HBA_SetRNIDMgmtInfo routine to program the HBA to return the indicated request node identification information data (RNID). |
| [HBA_PortAttributes structure](ns-hbaapi-hba_portattributes.md) | The structure is used by the HBA_GetPortAttributesByWWN fibre channel HBA library routine to report the attributes for a specified remote fibre channel port. |
| [HBA_PortStatistics structure](ns-hbaapi-hba_portstatistics.md) | The HBA_PortStatistics structure contains statistical information about a port. |
| [HBA_Pty_EventInfo structure](ns-hbaapi-hba_pty_eventinfo.md) | The HBA_Link_EventInfo structure contains information about a WMI proprietary event associated with the fibre channel HBA API. |
| [HBA_RSCN_EventInfo structure](ns-hbaapi-hba_rscn_eventinfo.md) | The HBA_Link_EventInfo structure contains information about a WMI RSCN event associated with the fibre channel HBA API. |
| [HBA_ScsiId structure](ns-hbaapi-hba_scsiid.md) | The HBA_ScsiId structure contains information used by the operating system to identify a SCSI logical unit. |
| [HBA_fc4types structure](ns-hbaapi-hba_fc4types.md) | The HBA_fc4types structure contains a set of up to 32 values indicating the FC-4 types that the HBA supports. |
| [HBA_ipaddress structure](ns-hbaapi-hba_ipaddress.md) | The HBA_ipaddress structure specifies an IP address in a way that is independent of the version of the IP protocol in use. |
| [HBA_wwn structure](ns-hbaapi-hba_wwn.md) | The HBA_wwn structure contains a 64 bit world-wide name (WWN) that uniquely identifies an HBA. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [HBA_wwntype enumeration](ne-hbaapi-hba_wwntype.md) | The HBA_wwntype enumerator indicates whether a worldwide name specifies a port or a node (machine). |
