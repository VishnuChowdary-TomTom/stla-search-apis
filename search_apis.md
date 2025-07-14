# API Reference

# Table of Contents
































































































- Services
    - [AutocompleteService](#stellantisgeoplatformsearchv1autocompleteservice)
  









- Services
    - [DestinationService](#stellantisgeoplatformsearchv1destinationservice)
  





 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



# AutocompleteService {#stellantisgeoplatformsearchv1autocompleteservice}
Autocomplete RPC Service. Use it to get performant suggestions for a given text query.

## Autocomplete

> **rpc** Autocomplete([AutocompleteRequest](#autocompleterequest))
    [AutocompleteResponse](#autocompleteresponse)

Request suggestions for a given text query. The `AutocompleteRequest` allows specifying query configurations, while
the `AutocompleteResponse` contains a list of suggestions with additional details about each one.
 <!-- end methods -->
 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



 <!-- end services -->



# DestinationService {#stellantisgeoplatformsearchv1destinationservice}


## Search

> **rpc** Search([SearchRequest](#searchrequest))
    [SearchResponse](#searchresponse)

A customer method due to need of encoding advanced query semantics.
## GetById

> **rpc** GetById([GetByIdRequest](#getbyidrequest))
    [GetByIdResponse](#getbyidresponse)


## GetDynamicSearchCriteria

> **rpc** GetDynamicSearchCriteria([GetDynamicSearchCriteriaRequest](#getdynamicsearchcriteriarequest))
    [GetDynamicSearchResponse](#getdynamicsearchresponse)


 <!-- end methods -->
 <!-- end services -->

 <!-- end Files -->

# Messages


## Boundingbox {#boundingbox}


| Field | Type | Description |
| ----- | ---- | ----------- |
| south | [ double](#double) | The incident bounding box south latitude coordinate as float. |
| west | [ double](#double) | The incident bounding box west longitude coordinate as float. |
| north | [ double](#double) | The incident bounding box north latitude coordinate as float. |
| east | [ double](#double) | The incident bounding box east longitude coordinate as float. |



## Coordinate {#coordinate}


| Field | Type | Description |
| ----- | ---- | ----------- |
| latitude | [ double](#double) | Precision up to 64 bits. For data transport purposes only. |
| longitude | [ double](#double) | Precision up to 64 bits. For data transport purposes only. |





## DataLayerId {#datalayerid}


| Field | Type | Description |
| ----- | ---- | ----------- |
| layer_id | [ string](#string) | none |





## DateTimeDescriptor {#datetimedescriptor}
ISO 8601

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ DateTimeDescriptorType](#datetimedescriptortype) | none |
| value | [ string](#string) | none |





## Currency {#currency}


| Field | Type | Description |
| ----- | ---- | ----------- |
| currency_code | [ string](#string) | none |



## Money {#money}


| Field | Type | Description |
| ----- | ---- | ----------- |
| currency | [ Currency](#currency) | Currency code as per ISO 4217. https://en.wikipedia.org/wiki/ISO_4217 |
| units | [ int64](#int64) | The whole units of the amount. For example if `currencyCode` is `"USD"`, then 1 unit is one US dollar. |
| nanos | [ int32](#int32) | Number of nano (10^-9) units of the amount. The value must be between -999,999,999 and +999,999,999 inclusive. If `units` is positive, `nanos` must be positive or zero. If `units` is zero, `nanos` can be positive, zero, or negative. If `units` is negative, `nanos` must be negative or zero. For example $-1.75 is represented as `units`=-1 and `nanos`=-750,000,000. |





## TimeZone {#timezone}
Represents a time zone from the
[IANA Time Zone Database](https://www.iana.org/time-zones).

| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | IANA Time Zone Database time zone, e.g. "America/New_York" |





## DealershipDynamicCriteria {#dealershipdynamiccriteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| car_brand_criteria | [repeated DynamicCriteriaEntry](#dynamiccriteriaentry) | none |
| revision_tag | [ string](#string) | none |



## DynamicCriteriaEntry {#dynamiccriteriaentry}


| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ string](#string) | none |
| label | [ string](#string) | none |



## EvChargerDynamicCriteria {#evchargerdynamiccriteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| provider_criteria | [repeated DynamicCriteriaEntry](#dynamiccriteriaentry) | none |
| revision_tag | [ string](#string) | none |





## Dealership {#dealership}


| Field | Type | Description |
| ----- | ---- | ----------- |
| car_brand | [ stellantis.geo.platform.search.v1.DynamicCriteriaEntry](#stellantisgeoplatformsearchv1dynamiccriteriaentry) | none |
| car_brands | [map stellantis.geo.platform.search.v1.DynamicCriteriaEntry](#stellantisgeoplatformsearchv1dynamiccriteriaentry) | none |





































## EVBatteryChargingCurve {#evbatterychargingcurve}


| Field | Type | Description |
| ----- | ---- | ----------- |
| state_of_charge | [ double](#double) | charge level in watt-hour |
| max_power | [ double](#double) | maximum battery charging rate in watt. |



## EVChargingParameters {#evchargingparameters}


| Field | Type | Description |
| ----- | ---- | ----------- |
| charging_curve | [repeated EVBatteryChargingCurve](#evbatterychargingcurve) | specifies the maximum battery charging rate (W) at a given charge level (Wh) in a list of pairs. |
| unconditioned_charging_curve | [repeated EVBatteryChargingCurve](#evbatterychargingcurve) | specifies the maximum battery charging rate (W) at a specified charge level (Wh) in a list of pairs when the battery is in an unconditioned state (for example, cold). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _pre_conditioning_time.pre_conditioning_time | [optional double](#double) | Optional parameter that defines the time in sec it would take for the vehicle's battery to condition. |
| ev_connector_types | [repeated EvConnectorType](#evconnectortype) | Required parameter that defines the compatible connector-types for the vehicle. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _max_voltage.max_voltage | [optional double](#double) | max voltage supported by battery in voltage |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _max_current.max_current | [optional double](#double) | max current supported by battery in amp |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _max_charging_power.max_charging_power | [optional double](#double) | max power supported by battery in watt |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _max_ac_charging_power.max_ac_charging_power | [optional double](#double) | specify maximum AC charging power(W) that can be delivered by the onboard vehicle charger. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _efficiency.efficiency | [optional double](#double) | efficiency factor for charging |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _baseload.baseload | [optional double](#double) | Baseload of the battery in watt. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _charging_time_offset.charging_time_offset | [optional double](#double) | Addiotional time needed(in sec) after and before charging. |



## EVEnergyConsumptionCurve {#evenergyconsumptioncurve}


| Field | Type | Description |
| ----- | ---- | ----------- |
| speed | [ double](#double) | vehicle speed in km/h |
| consumption | [ double](#double) | energy consumption in watt-hours |



## EVRoutingParameters {#evroutingparameters}
Parameters for Electric Vehicle Routing

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _ev_initial_charge.ev_initial_charge | [optional double](#double) | specify initial charge of vehicle in Wh (watt-hours) at the beginning of the route. The default value is equal to ev_max_charge. |
| ev_max_charge | [ double](#double) | Required parameter that defines the maximum possible charge of vehicle in Wh (watt-hours). |
| free_flow_energy_consumption_curve | [repeated EVEnergyConsumptionCurve](#evenergyconsumptioncurve) | Required parameter that specifies in pairs the energy consumption in watt-hours per kilometer at a given free flow speed in kph. |
| traffic_energy_consumption_curve | [repeated EVEnergyConsumptionCurve](#evenergyconsumptioncurve) | Required parameter that specifies in pairs the energy consumption in watt-hours per kilometer at a given speed in kph under traffic condition |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _auxiliary_consumption.auxiliary_consumption | [optional double](#double) | Optional parameter to define the measure of the continuous power draw of the auxiliary systems (e.g heating, radio, air conditioning) in watts. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _ev_ascent_consumption.ev_ascent_consumption | [optional double](#double) | amount of energy an electric vehicle consumes from increasing elevation(watts-hours per meter). Max value is 1000 Wh/m and min value is 0 Wh/m. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _ev_descent_recovery.ev_descent_recovery | [optional double](#double) | amount of energy an electric vehicle gains from decreasing elevation(watts-hours per meter). Max value is 1000 Wh/m and min value is 0 Wh/m. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _ev_regeneration_efficiency.ev_regeneration_efficiency | [optional double](#double) | percentage of energy that goes back to battery during descent.Default 0.7 |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _ev_charging_parameters.ev_charging_parameters | [optional EVChargingParameters](#evchargingparameters) | Ev charging paramaters used to find teh charging station and calculate charging time. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _ev_min_charge_at_destination.ev_min_charge_at_destination | [optional double](#double) | define the minimum battery charge required at the final route destination (Wh). The default value is 10% of ev_max_charge. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _ev_min_charge_at_charging_station.ev_min_charge_at_charging_station | [optional double](#double) | Optional parameter to define the minimum charge when arriving at the charging station (Wh). The default value is 10% of ev_max_charge. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _ensureReachability.ensureReachability | [optional bool](#bool) | Optional parameter to specify whether EV route should add charging stops to make the route rechable. |



## EvCharger {#evcharger}


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| ownership | [ EvOwnership](#evownership) | none |
| status | [ EvStatus](#evstatus) | none |
| capabilities | [repeated EvCapabilities](#evcapabilities) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _access_type.access_type | [optional EvAccessType](#evaccesstype) | none |
| connectors | [repeated EvConnector](#evconnector) | none |
| features | [repeated EvChargersFeature](#evchargersfeature) | none |
| payment_methods | [repeated EvChargersPaymentMethod](#evchargerspaymentmethod) | none |
| last_update_time | [ stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |



## EvChargingStation {#evchargingstation}


| Field | Type | Description |
| ----- | ---- | ----------- |
| chargers | [repeated EvCharger](#evcharger) | none |



## EvConnector {#evconnector}


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| format | [ EvConnectorFormat](#evconnectorformat) | none |
| connector_type | [ EvConnectorType](#evconnectortype) | none |
| power_type | [ EvPowerType](#evpowertype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _max_amperage.max_amperage | [optional int32](#int32) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _max_voltage.max_voltage | [optional int32](#int32) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _max_charge_rate_kw.max_charge_rate_kw | [optional double](#double) | none |
| tariffs | [repeated EvTariff](#evtariff) | none |
| last_update_time | [ stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |



## EvEnergyDimension {#evenergydimension}


| Field | Type | Description |
| ----- | ---- | ----------- |
| wh_step | [ sint32](#sint32) | none |



## EvOwnership {#evownership}


| Field | Type | Description |
| ----- | ---- | ----------- |
| emsp_value | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _operator.operator | [optional string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _sub_operator.sub_operator | [optional string](#string) | none |
| emsp | [map stellantis.geo.platform.search.v1.DynamicCriteriaEntry](#stellantisgeoplatformsearchv1dynamiccriteriaentry) | none |



## EvPriceComponent {#evpricecomponent}


| Field | Type | Description |
| ----- | ---- | ----------- |
| price | [ stellantis.geo.platform.common.v1.Money](#stellantisgeoplatformcommonv1money) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) dimension.flat | [ google.protobuf.Empty](#googleprotobufempty) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) dimension.energy | [ EvEnergyDimension](#evenergydimension) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) dimension.time | [ EvTimeDimension](#evtimedimension) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) dimension.parking_time | [ EvTimeDimension](#evtimedimension) | none |



## EvTariff {#evtariff}


| Field | Type | Description |
| ----- | ---- | ----------- |
| elements | [repeated EvTariffElement](#evtariffelement) | none |
| last_update_time | [ stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |



## EvTariffElement {#evtariffelement}


| Field | Type | Description |
| ----- | ---- | ----------- |
| price_components | [repeated EvPriceComponent](#evpricecomponent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _restriction.restriction | [optional EvTariffRestriction](#evtariffrestriction) | none |



## EvTariffRestriction {#evtariffrestriction}


| Field | Type | Description |
| ----- | ---- | ----------- |
| date_times | [repeated stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _min_kwh.min_kwh | [optional float](#float) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _max_kwh.max_kwh | [optional float](#float) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _min_power_kw.min_power_kw | [optional float](#float) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _max_power_kw.max_power_kw | [optional float](#float) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _duration.duration | [optional stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |



## EvTimeDimension {#evtimedimension}


| Field | Type | Description |
| ----- | ---- | ----------- |
| duration_step | [ stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |





## DisplayText {#displaytext}


| Field | Type | Description |
| ----- | ---- | ----------- |
| language | [ string](#string) | none |
| text | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## AdditionalGeoLocation {#additionalgeolocation}


| Field | Type | Description |
| ----- | ---- | ----------- |
| latitude | [ string](#string) | none |
| longitude | [ string](#string) | none |
| name | [ DisplayText](#displaytext) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## Image {#image}


| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | none |
| thumbnail | [ string](#string) | none |
| category | [ stellantis.geo.platform.domain.eves.v1.enums.ImageCategory](#stellantisgeoplatformdomainevesv1enumsimagecategory) | none |
| type | [ string](#string) | none |
| width | [ string](#string) | none |
| height | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## BusinessDetails {#businessdetails}


| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | none |
| website | [ string](#string) | none |
| logo | [ Image](#image) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## EnergySource {#energysource}


| Field | Type | Description |
| ----- | ---- | ----------- |
| source | [ stellantis.geo.platform.domain.eves.v1.enums.EnergySourceCategory](#stellantisgeoplatformdomainevesv1enumsenergysourcecategory) | none |
| percentage | [ float](#float) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## EnvironmentalImpact {#environmentalimpact}


| Field | Type | Description |
| ----- | ---- | ----------- |
| amount | [ float](#float) | none |
| category | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## EnergyMix {#energymix}


| Field | Type | Description |
| ----- | ---- | ----------- |
| is_green_energy | [ bool](#bool) | none |
| energy_sources | [repeated EnergySource](#energysource) | none |
| environ_impact | [repeated EnvironmentalImpact](#environmentalimpact) | none |
| supplier_name | [ string](#string) | none |
| energy_product_name | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## Connector {#connector}


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| standard | [ stellantis.geo.platform.domain.eves.v1.enums.ConnectorType](#stellantisgeoplatformdomainevesv1enumsconnectortype) | none |
| format | [ stellantis.geo.platform.domain.eves.v1.enums.ConnectorFormat](#stellantisgeoplatformdomainevesv1enumsconnectorformat) | none |
| power_type | [ stellantis.geo.platform.domain.eves.v1.enums.PowerType](#stellantisgeoplatformdomainevesv1enumspowertype) | none |
| max_voltage | [ int32](#int32) | none |
| max_amperage | [ int32](#int32) | none |
| max_electric_power | [ int32](#int32) | none |
| tariff_ids | [repeated string](#string) | none |
| terms_and_conditions | [ string](#string) | none |
| last_updated | [ stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## StatusSchedule {#statusschedule}


| Field | Type | Description |
| ----- | ---- | ----------- |
| period_begin | [ string](#string) | none |
| period_end | [ string](#string) | none |
| status | [ stellantis.geo.platform.domain.eves.v1.enums.Status](#stellantisgeoplatformdomainevesv1enumsstatus) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## Evse {#evse}


| Field | Type | Description |
| ----- | ---- | ----------- |
| uid | [ string](#string) | none |
| evse_id | [ string](#string) | none |
| status | [ stellantis.geo.platform.domain.eves.v1.enums.Status](#stellantisgeoplatformdomainevesv1enumsstatus) | none |
| status_schedule | [repeated StatusSchedule](#statusschedule) | none |
| capabilities | [repeated stellantis.geo.platform.domain.eves.v1.enums.Capability](#stellantisgeoplatformdomainevesv1enumscapability) | none |
| connectors | [repeated Connector](#connector) | none |
| floor_level | [ string](#string) | none |
| coordinates | [ stellantis.geo.platform.common.v1.Coordinate](#stellantisgeoplatformcommonv1coordinate) | none |
| physical_reference | [ string](#string) | none |
| directions | [repeated DisplayText](#displaytext) | none |
| parking_restrictions | [repeated stellantis.geo.platform.domain.eves.v1.enums.ParkingRestriction](#stellantisgeoplatformdomainevesv1enumsparkingrestriction) | none |
| images | [repeated Image](#image) | none |
| last_updated | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
| payment_methods | [repeated string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## ExceptionalPeriod {#exceptionalperiod}


| Field | Type | Description |
| ----- | ---- | ----------- |
| period_begin | [ string](#string) | none |
| period_end | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## RegularHours {#regularhours}


| Field | Type | Description |
| ----- | ---- | ----------- |
| weekday | [ int32](#int32) | none |
| period_begin | [ string](#string) | none |
| period_end | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## Hours {#hours}


| Field | Type | Description |
| ----- | ---- | ----------- |
| twenty_four_seven | [ bool](#bool) | none |
| regular_hours | [repeated RegularHours](#regularhours) | none |
| exceptional_openings | [repeated ExceptionalPeriod](#exceptionalperiod) | none |
| exceptional_closings | [repeated ExceptionalPeriod](#exceptionalperiod) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## PublishTokenType {#publishtokentype}


| Field | Type | Description |
| ----- | ---- | ----------- |
| uid | [ string](#string) | none |
| type | [ stellantis.geo.platform.domain.eves.v1.enums.TokenType](#stellantisgeoplatformdomainevesv1enumstokentype) | none |
| visual_number | [ string](#string) | none |
| issuer | [ string](#string) | none |
| group_id | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## Location {#location}


| Field | Type | Description |
| ----- | ---- | ----------- |
| country_code | [ string](#string) | none |
| party_id | [ string](#string) | none |
| id | [ string](#string) | none |
| publish | [ bool](#bool) | none |
| publish_allowed_to | [repeated valueobject.PublishTokenType](#valueobjectpublishtokentype) | none |
| name | [ string](#string) | none |
| address | [ string](#string) | none |
| city | [ string](#string) | none |
| postal_code | [ string](#string) | none |
| state | [ string](#string) | none |
| country | [ string](#string) | none |
| coordinates | [ stellantis.geo.platform.common.v1.Coordinate](#stellantisgeoplatformcommonv1coordinate) | none |
| related_locations | [repeated valueobject.AdditionalGeoLocation](#valueobjectadditionalgeolocation) | none |
| parking_type | [ enums.ParkingType](#enumsparkingtype) | none |
| evses | [repeated valueobject.Evse](#valueobjectevse) | none |
| directions | [repeated valueobject.DisplayText](#valueobjectdisplaytext) | none |
| operator | [ valueobject.BusinessDetails](#valueobjectbusinessdetails) | none |
| suboperator | [ valueobject.BusinessDetails](#valueobjectbusinessdetails) | none |
| owner | [ valueobject.BusinessDetails](#valueobjectbusinessdetails) | none |
| facilities | [repeated enums.Facility](#enumsfacility) | none |
| time_zone | [ string](#string) | none |
| opening_times | [ valueobject.Hours](#valueobjecthours) | none |
| charging_when_closed | [ bool](#bool) | none |
| images | [repeated valueobject.Image](#valueobjectimage) | none |
| energy_mix | [ valueobject.EnergyMix](#valueobjectenergymix) | none |
| last_updated | [ stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## LocationUpdate {#locationupdate}


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| ocpi_location | [ Location](#location) | none |





## Price {#price}


| Field | Type | Description |
| ----- | ---- | ----------- |
| excl_vat | [ float](#float) | none |
| incl_vat | [ float](#float) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## PriceComponent {#pricecomponent}


| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ string](#string) | none |
| price | [ float](#float) | none |
| vat | [ float](#float) | none |
| stepSize | [ int32](#int32) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## TariffRestrictions {#tariffrestrictions}


| Field | Type | Description |
| ----- | ---- | ----------- |
| startTime | [ string](#string) | none |
| endTime | [ string](#string) | none |
| startDate | [ string](#string) | none |
| endDate | [ string](#string) | none |
| minKwh | [ float](#float) | none |
| maxKwh | [ float](#float) | none |
| minCurrent | [ float](#float) | none |
| maxCurrent | [ float](#float) | none |
| minPower | [ float](#float) | none |
| maxPower | [ float](#float) | none |
| minDuration | [ int32](#int32) | none |
| maxDuration | [ int32](#int32) | none |
| dayOfWeek | [repeated stellantis.geo.platform.domain.eves.v1.enums.DayOfWeek](#stellantisgeoplatformdomainevesv1enumsdayofweek) | none |
| reservation | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## TariffElement {#tariffelement}


| Field | Type | Description |
| ----- | ---- | ----------- |
| priceComponents | [repeated PriceComponent](#pricecomponent) | none |
| restrictions | [ TariffRestrictions](#tariffrestrictions) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## Tariff {#tariff}


| Field | Type | Description |
| ----- | ---- | ----------- |
| countryCode | [ string](#string) | none |
| partyId | [ string](#string) | none |
| id | [ string](#string) | none |
| currency | [ string](#string) | none |
| type | [ enums.TariffType](#enumstarifftype) | none |
| tariffAltText | [repeated valueobject.DisplayText](#valueobjectdisplaytext) | none |
| tariffAltUrl | [ string](#string) | none |
| minPrice | [ valueobject.Price](#valueobjectprice) | none |
| maxPrice | [ valueobject.Price](#valueobjectprice) | none |
| elements | [repeated valueobject.TariffElement](#valueobjecttariffelement) | none |
| startDateTime | [ stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |
| endDateTime | [ stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |
| energyMix | [ valueobject.EnergyMix](#valueobjectenergymix) | none |
| lastUpdated | [ stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _other_fields_json.other_fields_json | [optional string](#string) | none |





## Parking {#parking}


| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ ParkingType](#parkingtype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _fee.fee | [optional Fee](#fee) | none |





## Address {#address}


| Field | Type | Description |
| ----- | ---- | ----------- |
| formatted_address | [ string](#string) | none |
| address_components | [map Address.AddressComponentsEntry](#addressaddresscomponentsentry) | none |



## Address.AddressComponentsEntry {#addressaddresscomponentsentry}


| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |



## Polygon {#polygon}


| Field | Type | Description |
| ----- | ---- | ----------- |
| areas | [repeated stellantis.geo.platform.common.v1.Coordinate](#stellantisgeoplatformcommonv1coordinate) | none |



## Route {#route}


| Field | Type | Description |
| ----- | ---- | ----------- |
| coordinates | [repeated stellantis.geo.platform.common.v1.Coordinate](#stellantisgeoplatformcommonv1coordinate) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _radius.radius | [optional double](#double) | none |



## Vicinity {#vicinity}


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) place.point | [ stellantis.geo.platform.common.v1.Coordinate](#stellantisgeoplatformcommonv1coordinate) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) place.locality | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _radius.radius | [optional double](#double) | none |





## AutocompleteRequest {#autocompleterequest}
Request message for the `Autocomplete` RPC in the `AutocompleteService`.

| Field | Type | Description |
| ----- | ---- | ----------- |
| text_query | [ string](#string) | A text query to get suggestions for. For generic suggestions not biased by any text, leave this field as an empty string. For the sake of clarity, the generic suggestions are still relevant in other terms like other request parameters or authenticated client (determined by the authentication method). |
| requester_position | [ stellantis.geo.platform.common.v1.Coordinate](#stellantisgeoplatformcommonv1coordinate) | Describes current requester gps position. If in_vicinity won't be provided then requester_position will be used to fulfill request. If both are set, then in_vicinity will be used to fulfill request. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _in_vicinity.in_vicinity | [optional Vicinity](#vicinity) | Specifies region which will be used as context for autocomplete. Useful when user want more contextual suggestions for different place than it actually is. If not specified then requester_position will be used as contextual position. NOTE: Locality from Vicinity message currently is not supported! |
| language_code | [ string](#string) | The language code as per IETF BCP 47 determines the language of the suggestions returned. If the language is not supported, the error gRPC status code will be returned. |



## AutocompleteResponse {#autocompleteresponse}
Request message for the `Autocomplete` RPC in the `AutocompleteService`.

| Field | Type | Description |
| ----- | ---- | ----------- |
| suggestions | [repeated AutocompleteSuggestion](#autocompletesuggestion) | none |



## AutocompleteSuggestion {#autocompletesuggestion}
Message represents a human readable suggestion with a primary as well as optional secondary text.

Suggestion might be explicit or implicit. We name suggestion explicit if, and only if, the `primary_text` is partially
or fully matched by the `text_query` of the `AutocompleteRequest`. All other cases are considered implicit, with most
common example being a suggestion semantically matching the `text_query`. While explicit queries are less fuzzy and
easier to understand, the implicit matches leaves the room for more sophisticated suggestion search techniques.

Note, the content of texts is very sensitive to `language_code` of the `AutocompleteRequest`.

| Field | Type | Description |
| ----- | ---- | ----------- |
| primary_text | [ string](#string) | The primary text of the suggestion. It is a human readable description of matched `text_query` of the `AutocompleteRequest`. If the match is explicit the `primary_text_matches`. More on explicit vs. implicit in the `AutocompleteSuggestion` documentation. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _secondary_text.secondary_text | [optional string](#string) | The secondary text of the suggestion is optional and represents a supplementary human readable description. The content of this field is heavily dependent on suggestions underlying data. When implementation populates this field it aims to increase distinction of the suggestion. A common example is adding the address to the explicit and popular name stored in `primary_text`. More on explicit vs. implicit in the `AutocompleteSuggestion` documentation. |
| primary_text_matches | [repeated MatchingRange](#matchingrange) | Contains all found matching sub string ranges of the `text_query` from the `AutocompleteRequest` in the `primary_text`. Non empty for explicit matches and always empty for implicit matches. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) details.place | [ SuggestedPlace](#suggestedplace) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) details.query | [ SuggestedQuery](#suggestedquery) | none |



## MatchingRange {#matchingrange}
An auxiliary information describing a range of a string by inclusive start index and exclusive end index.

| Field | Type | Description |
| ----- | ---- | ----------- |
| start_offset_inclusive | [ int32](#int32) | The zero-indexed and inclusive start index of the matched string. |
| end_offset_exclusive | [ int32](#int32) | The zero-indexed and exclusive end index of the matched string. |



## SuggestedPlace {#suggestedplace}
A details message representing a place. Usually it is an entity in real world or an
administrative entity like address, city, etc. To determine use the `types` field.
Use the `id` field to get more details about the place.

If the place was recently interacted with by the authenticated client the field
called `interacted_recently` will be set to true. The "interaction" meaning is
arbitrary and might be a result of multiple other systems reporting it.

| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | The unique identifier of the place. Use this identifier to get more details about the place for example by `GetByIdRequest` message. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _beeline_distance_meters.beeline_distance_meters | [optional int32](#int32) | A beeline distance denominated in meters from the `AutocompleteRequest` `Vicinity`. It is subject to implementation on how the distance is calculated. Number is always positive or 0. |
| interacted_recently | [ bool](#bool) | If the place was recently interacted with by the authenticated client the field will be set to true. The "interaction" meaning is arbitrary and might be a result of multiple other systems interactions on behalf of the authenticated client. |
| types | [repeated string](#string) | The types of the place. A list cannot be empty. Types are related to Google types and all possible values are listed here: https://developers.google.com/maps/documentation/places/web-service/place-types |



## SuggestedQuery {#suggestedquery}
A details message representing a query to search with.

| Field | Type | Description |
| ----- | ---- | ----------- |
| queried_recently | [ bool](#bool) | The suggestion can be a query suggested by the system or a recent query associated with the authenticated client (determined by the authentication method). The "recent" meaning is arbitrary and might be a result of multiple systems interactions on behalf od the authenticated client. |







## AmenityCriteria {#amenitycriteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| place_types | [repeated string](#string) | none |



## Criteria {#criteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _place_type_criteria.place_type_criteria | [optional PlaceTypeCriteria](#placetypecriteria) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _open_criteria.open_criteria | [optional OpenCriteria](#opencriteria) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _rating_criteria.rating_criteria | [optional RatingCriteria](#ratingcriteria) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _fuel_criteria.fuel_criteria | [optional FuelCriteria](#fuelcriteria) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _ev_charge_criteria.ev_charge_criteria | [optional EvChargerCriteria](#evchargercriteria) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _price_level_criteria.price_level_criteria | [optional PriceLevelCriteria](#pricelevelcriteria) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _parking_criteria.parking_criteria | [optional ParkingCriteria](#parkingcriteria) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _amenities_criteria.amenities_criteria | [optional AmenityCriteria](#amenitycriteria) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _dealership_criteria.dealership_criteria | [optional DealershipCriteria](#dealershipcriteria) | none |



## DealershipCriteria {#dealershipcriteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| car_brand | [ DynamicCriteriaEntry](#dynamiccriteriaentry) | none |



## EvChargerCriteria {#evchargercriteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| connector_types | [repeated stellantis.geo.platform.domain.eves.v1.EvConnectorType](#stellantisgeoplatformdomainevesv1evconnectortype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _status.status | [optional stellantis.geo.platform.domain.eves.v1.EvStatus](#stellantisgeoplatformdomainevesv1evstatus) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _emsp_value.emsp_value | [optional string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _operator.operator | [optional string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _min_charge_rate_kw.min_charge_rate_kw | [optional double](#double) | none |
| features | [repeated stellantis.geo.platform.domain.eves.v1.EvChargersFeature](#stellantisgeoplatformdomainevesv1evchargersfeature) | none |
| payment_methods | [repeated stellantis.geo.platform.domain.eves.v1.EvChargersPaymentMethod](#stellantisgeoplatformdomainevesv1evchargerspaymentmethod) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _max_charge_rate_kw.max_charge_rate_kw | [optional double](#double) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _open_twenty_four_seven.open_twenty_four_seven | [optional bool](#bool) | none |



## FuelCriteria {#fuelcriteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| fuel | [ FuelType](#fueltype) | none |



## GetByIdRequest {#getbyidrequest}


| Field | Type | Description |
| ----- | ---- | ----------- |
| ids | [repeated string](#string) | none |
| request_parameters | [ RequestParameters](#requestparameters) | none |



## GetDynamicSearchCriteriaRequest {#getdynamicsearchcriteriarequest}


| Field | Type | Description |
| ----- | ---- | ----------- |
| data_layer_id | [ stellantis.geo.platform.common.v1.DataLayerId](#stellantisgeoplatformcommonv1datalayerid) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _requester_position.requester_position | [optional stellantis.geo.platform.common.v1.Coordinate](#stellantisgeoplatformcommonv1coordinate) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _location_bias.location_bias | [optional Location](#location) | none |
| language_code | [ LanguageParameters](#languageparameters) | none |



## LanguageParameters {#languageparameters}


| Field | Type | Description |
| ----- | ---- | ----------- |
| language_code | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _script_code.script_code | [optional string](#string) | none |



## Location {#location}


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) where.in_vicinity | [ Vicinity](#vicinity) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) where.along_route | [ Route](#route) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) where.within_polygon | [ Polygon](#polygon) | none |



## OpenCriteria {#opencriteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) open.open_now | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) open.on_time | [ stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |



## ParkingCriteria {#parkingcriteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| parking_type | [ stellantis.geo.platform.domain.parking.v1.ParkingType](#stellantisgeoplatformdomainparkingv1parkingtype) | none |
| fee | [ stellantis.geo.platform.domain.parking.v1.Fee](#stellantisgeoplatformdomainparkingv1fee) | none |



## PlaceTypeCriteria {#placetypecriteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| place_types | [repeated string](#string) | none |



## PriceLevelCriteria {#pricelevelcriteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| price_levels | [repeated PriceLevel](#pricelevel) | none |



## RatingCriteria {#ratingcriteria}


| Field | Type | Description |
| ----- | ---- | ----------- |
| rating | [ double](#double) | none |



## RequestParameters {#requestparameters}


| Field | Type | Description |
| ----- | ---- | ----------- |
| request_time | [ stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |
| requester_position | [ stellantis.geo.platform.common.v1.Coordinate](#stellantisgeoplatformcommonv1coordinate) | none |
| language_code | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _response_limit.response_limit | [optional int32](#int32) | none |
| sorting_rank_biases | [repeated SortingRankBias](#sortingrankbias) | none |



## SearchRequest {#searchrequest}


| Field | Type | Description |
| ----- | ---- | ----------- |
| request_parameters | [ RequestParameters](#requestparameters) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _text_query.text_query | [optional string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _location_bias.location_bias | [optional Location](#location) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _search_criteria.search_criteria | [optional Criteria](#criteria) | none |





## AccessibilityFacilities {#accessibilityfacilities}


| Field | Type | Description |
| ----- | ---- | ----------- |
| has_accessibility_facilities | [ bool](#bool) | none |



## Author {#author}


| Field | Type | Description |
| ----- | ---- | ----------- |
| display_name | [ string](#string) | Name of the author of the Photo or Review. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _uri.uri | [optional string](#string) | URI of the author of the Photo or Review. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _photo_uri.photo_uri | [optional string](#string) | Profile photo URI of the author of the Photo or Review. |



## ContactInfo {#contactinfo}


| Field | Type | Description |
| ----- | ---- | ----------- |
| phone_number | [ string](#string) | none |
| email_address | [ string](#string) | none |
| additional_phone_numbers | [repeated string](#string) | none |
| additional_email_addresses | [repeated string](#string) | none |



## Destination {#destination}


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| name | [ string](#string) | none |
| types | [repeated PlaceType](#placetype) | none |
| coordinate | [ stellantis.geo.platform.common.v1.Coordinate](#stellantisgeoplatformcommonv1coordinate) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _address.address | [optional Address](#address) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _phone_number.phone_number | [optional PhoneNumber](#phonenumber) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _rating.rating | [optional double](#double) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _opens.opens | [optional Opens](#opens) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _price_level.price_level | [optional PriceLevel](#pricelevel) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _fuel_station.fuel_station | [optional FuelStation](#fuelstation) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _ev_chargers_station.ev_chargers_station | [optional stellantis.geo.platform.domain.eves.v1.EvChargingStation](#stellantisgeoplatformdomainevesv1evchargingstation) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _parking.parking | [optional stellantis.geo.platform.domain.parking.v1.Parking](#stellantisgeoplatformdomainparkingv1parking) | none |
| amenities | [repeated PlaceType](#placetype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _beeline_distance_meters.beeline_distance_meters | [optional double](#double) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _user_ratings.user_ratings | [optional UserRatings](#userratings) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _accessibility_facilities.accessibility_facilities | [optional AccessibilityFacilities](#accessibilityfacilities) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _dealership.dealership | [optional stellantis.geo.platform.domain.dealerships.v1.Dealership](#stellantisgeoplatformdomaindealershipsv1dealership) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _contact_info.contact_info | [optional ContactInfo](#contactinfo) | none |
| photos | [repeated Photo](#photo) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _time_zone.time_zone | [optional stellantis.geo.platform.common.v1.TimeZone](#stellantisgeoplatformcommonv1timezone) | none |



## FuelStation {#fuelstation}


| Field | Type | Description |
| ----- | ---- | ----------- |
| fuels | [repeated FuelStation.Fuel](#fuelstationfuel) | none |



## FuelStation.Fuel {#fuelstationfuel}


| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ FuelType](#fueltype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _price.price | [optional stellantis.geo.platform.common.v1.Money](#stellantisgeoplatformcommonv1money) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _sub_type.sub_type | [optional string](#string) | none |



## GetByIdResponse {#getbyidresponse}


| Field | Type | Description |
| ----- | ---- | ----------- |
| destinations | [repeated Destination](#destination) | none |



## GetDynamicSearchResponse {#getdynamicsearchresponse}


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) data_layer_criteria.ev_charger_dynamic_criteria | [ EvChargerDynamicCriteria](#evchargerdynamiccriteria) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) data_layer_criteria.dealership_dynamic_criteria | [ DealershipDynamicCriteria](#dealershipdynamiccriteria) | none |



## Opens {#opens}


| Field | Type | Description |
| ----- | ---- | ----------- |
| open_now | [ bool](#bool) | none |
| week_openings | [repeated stellantis.geo.platform.common.v1.DateTimeDescriptor](#stellantisgeoplatformcommonv1datetimedescriptor) | none |



## PhoneNumber {#phonenumber}


| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) | none |



## Photo {#photo}
Photo information for a destination

| Field | Type | Description |
| ----- | ---- | ----------- |
| uri | [ string](#string) | URI to download photo |
| width | [ int32](#int32) | The width of the photo that is available in server |
| height | [ int32](#int32) | The height of the photo that is available in server |
| authors | [repeated Author](#author) | Provides information about photo authors |



## PlaceType {#placetype}


| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ string](#string) | The types of the place. A list cannot be empty. Types are related to Google types and all possible values are listed here: https://developers.google.com/maps/documentation/places/web-service/place-types |



## SearchResponse {#searchresponse}


| Field | Type | Description |
| ----- | ---- | ----------- |
| findings | [repeated Destination](#destination) | none |



## UserRatings {#userratings}


| Field | Type | Description |
| ----- | ---- | ----------- |
| rating | [ double](#double) | none |
| num_of_reviews | [ int32](#int32) | none |







# Enums





## DateTimeDescriptorType {#datetimedescriptortype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| DATE_TIME_DESCRIPTOR_TYPE_UNSPECIFIED | 0 | none |

| DATE_TIME_DESCRIPTOR_TYPE_DATE | 1 | none |

| DATE_TIME_DESCRIPTOR_TYPE_TIME | 2 | none |

| DATE_TIME_DESCRIPTOR_TYPE_DATE_TIME | 3 | none |

| DATE_TIME_DESCRIPTOR_TYPE_DURATION | 4 | none |

| DATE_TIME_DESCRIPTOR_TYPE_INTERVAL | 5 | none |











## Capability {#capability}

| Name | Number | Description |
| ---- | ------ | ----------- |

| CAPABILITY_UNSPECIFIED | 0 | none |

| CAPABILITY_CHARGING_PROFILE_CAPABLE | 1 | none |

| CAPABILITY_CHARGING_PREFERENCES_CAPABLE | 2 | none |

| CAPABILITY_CHIP_CARD_SUPPORT | 3 | none |

| CAPABILITY_CONTACTLESS_CARD_SUPPORT | 4 | none |

| CAPABILITY_CREDIT_CARD_PAYABLE | 5 | none |

| CAPABILITY_DEBIT_CARD_PAYABLE | 6 | none |

| CAPABILITY_PED_TERMINAL | 7 | none |

| CAPABILITY_REMOTE_START_STOP_CAPABLE | 8 | none |

| CAPABILITY_RESERVABLE | 9 | none |

| CAPABILITY_RFID_READER | 10 | none |

| CAPABILITY_START_SESSION_CONNECTOR_REQUIRED | 11 | none |

| CAPABILITY_TOKEN_GROUP_CAPABLE | 12 | none |

| CAPABILITY_UNLOCK_CAPABLE | 13 | none |



## ConnectorFormat {#connectorformat}

| Name | Number | Description |
| ---- | ------ | ----------- |

| CONNECTOR_FORMAT_UNSPECIFIED | 0 | none |

| CONNECTOR_FORMAT_SOCKET | 1 | none |

| CONNECTOR_FORMAT_CABLE | 2 | none |



## ConnectorType {#connectortype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| CONNECTOR_TYPE_UNSPECIFIED | 0 | none |

| CONNECTOR_TYPE_CHADEMO | 1 | none |

| CONNECTOR_TYPE_CHAOJI | 2 | none |

| CONNECTOR_TYPE_DOMESTIC_A | 3 | none |

| CONNECTOR_TYPE_DOMESTIC_B | 4 | none |

| CONNECTOR_TYPE_DOMESTIC_C | 5 | none |

| CONNECTOR_TYPE_DOMESTIC_D | 6 | none |

| CONNECTOR_TYPE_DOMESTIC_E | 7 | none |

| CONNECTOR_TYPE_DOMESTIC_F | 8 | none |

| CONNECTOR_TYPE_DOMESTIC_G | 9 | none |

| CONNECTOR_TYPE_DOMESTIC_H | 10 | none |

| CONNECTOR_TYPE_DOMESTIC_I | 11 | none |

| CONNECTOR_TYPE_DOMESTIC_J | 12 | none |

| CONNECTOR_TYPE_DOMESTIC_K | 13 | none |

| CONNECTOR_TYPE_DOMESTIC_L | 14 | none |

| CONNECTOR_TYPE_DOMESTIC_M | 15 | none |

| CONNECTOR_TYPE_DOMESTIC_N | 16 | none |

| CONNECTOR_TYPE_DOMESTIC_O | 17 | none |

| CONNECTOR_TYPE_GBT_AC | 18 | none |

| CONNECTOR_TYPE_GBT_DC | 19 | none |

| CONNECTOR_TYPE_IEC_60309_2_single_16 | 20 | none |

| CONNECTOR_TYPE_IEC_60309_2_three_16 | 21 | none |

| CONNECTOR_TYPE_IEC_60309_2_three_32 | 22 | none |

| CONNECTOR_TYPE_IEC_60309_2_three_64 | 23 | none |

| CONNECTOR_TYPE_IEC_62196_T1 | 24 | none |

| CONNECTOR_TYPE_IEC_62196_T1_COMBO | 25 | none |

| CONNECTOR_TYPE_IEC_62196_T2 | 26 | none |

| CONNECTOR_TYPE_IEC_62196_T2_COMBO | 27 | none |

| CONNECTOR_TYPE_IEC_62196_T3A | 28 | none |

| CONNECTOR_TYPE_IEC_62196_T3C | 29 | none |

| CONNECTOR_TYPE_NEMA_5_20 | 30 | none |

| CONNECTOR_TYPE_NEMA_6_30 | 31 | none |

| CONNECTOR_TYPE_NEMA_6_50 | 32 | none |

| CONNECTOR_TYPE_NEMA_10_30 | 33 | none |

| CONNECTOR_TYPE_NEMA_10_50 | 34 | none |

| CONNECTOR_TYPE_NEMA_14_30 | 35 | none |

| CONNECTOR_TYPE_NEMA_14_50 | 36 | none |

| CONNECTOR_TYPE_PANTOGRAPH_BOTTOM_UP | 37 | none |

| CONNECTOR_TYPE_PANTOGRAPH_TOP_DOWN | 38 | none |

| CONNECTOR_TYPE_TESLA_R | 39 | none |

| CONNECTOR_TYPE_TESLA_S | 40 | none |



## DayOfWeek {#dayofweek}

| Name | Number | Description |
| ---- | ------ | ----------- |

| DAY_OF_WEEK_UNSPECIFIED | 0 | none |

| DAY_OF_WEEK_MONDAY | 1 | none |

| DAY_OF_WEEK_TUESDAY | 2 | none |

| DAY_OF_WEEK_WEDNESDAY | 3 | none |

| DAY_OF_WEEK_THURSDAY | 4 | none |

| DAY_OF_WEEK_FRIDAY | 5 | none |

| DAY_OF_WEEK_SATURDAY | 6 | none |

| DAY_OF_WEEK_SUNDAY | 7 | none |



## EnergySourceCategory {#energysourcecategory}

| Name | Number | Description |
| ---- | ------ | ----------- |

| ENERGY_SOURCE_CATEGORY_UNSPECIFIED | 0 | none |

| ENERGY_SOURCE_CATEGORY_GENERAL_FOSSIL | 1 | none |

| ENERGY_SOURCE_CATEGORY_COAL | 2 | none |

| ENERGY_SOURCE_CATEGORY_GAS | 3 | none |

| ENERGY_SOURCE_CATEGORY_GENERAL_GREEN | 4 | none |

| ENERGY_SOURCE_CATEGORY_SOLAR | 5 | none |

| ENERGY_SOURCE_CATEGORY_WIND | 6 | none |

| ENERGY_SOURCE_CATEGORY_WATER | 7 | none |

| ENERGY_SOURCE_CATEGORY_NUCLEAR | 8 | none |



## EnvironmentalImpactCategory {#environmentalimpactcategory}

| Name | Number | Description |
| ---- | ------ | ----------- |

| ENVIRONMENTAL_IMPACT_CATEGORY_UNSPECIFIED | 0 | none |

| ENVIRONMENTAL_IMPACT_CATEGORY_NUCLEAR_WASTE | 1 | none |

| ENVIRONMENTAL_IMPACT_CATEGORY_CARBON_DIOXIDE | 2 | none |



## Facility {#facility}

| Name | Number | Description |
| ---- | ------ | ----------- |

| FACILITY_UNSPECIFIED | 0 | none |

| FACILITY_RESTAURANT | 1 | none |

| FACILITY_CAFE | 2 | none |

| FACILITY_MALL | 3 | none |

| FACILITY_SUPERMARKET | 4 | none |

| FACILITY_SPORT | 5 | none |

| FACILITY_RECREATION_AREA | 6 | none |

| FACILITY_NATURE | 7 | none |

| FACILITY_MUSEUM | 8 | none |

| FACILITY_BIKE_SHARING | 9 | none |

| FACILITY_BUS_STOP | 10 | none |

| FACILITY_TAXI_STAND | 11 | none |

| FACILITY_TRAM_STOP | 12 | none |

| FACILITY_METRO_STATION | 13 | none |

| FACILITY_TRAIN_STATION | 14 | none |

| FACILITY_AIRPORT | 15 | none |

| FACILITY_PARKING_LOT | 16 | none |

| FACILITY_CARPOOL_PARKING | 17 | none |

| FACILITY_FUEL_STATION | 18 | none |

| FACILITY_WIFI | 19 | none |

| FACILITY_HOTEL | 20 | none |



## ImageCategory {#imagecategory}

| Name | Number | Description |
| ---- | ------ | ----------- |

| IMAGE_CATEGORY_UNSPECIFIED | 0 | none |

| IMAGE_CATEGORY_ENTRANCE | 1 | none |

| IMAGE_CATEGORY_LOCATION | 2 | none |

| IMAGE_CATEGORY_NETWORK | 3 | none |

| IMAGE_CATEGORY_OPERATOR | 4 | none |

| IMAGE_CATEGORY_OTHER | 5 | none |

| IMAGE_CATEGORY_OWNER | 6 | none |

| IMAGE_CATEGORY_CHARGER | 7 | none |



## ParkingRestriction {#parkingrestriction}

| Name | Number | Description |
| ---- | ------ | ----------- |

| PARKING_RESTRICTION_UNSPECIFIED | 0 | none |

| PARKING_RESTRICTION_PLUGGED | 1 | none |

| PARKING_RESTRICTION_DISABLED | 2 | none |

| PARKING_RESTRICTION_CUSTOMERS | 3 | none |

| PARKING_RESTRICTION_MOTORCYCLES | 4 | none |

| PARKING_RESTRICTION_EV_ONLY | 5 | none |



## ParkingType {#parkingtype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| PARKING_TYPE_UNSPECIFIED | 0 | none |

| PARKING_TYPE_PARKING_GARAGE | 1 | none |

| PARKING_TYPE_PARKING_LOT | 2 | none |

| PARKING_TYPE_ON_DRIVEWAY | 3 | none |

| PARKING_TYPE_ON_STREET | 4 | none |

| PARKING_TYPE_UNDERGROUND_GARAGE | 5 | none |

| PARKING_TYPE_ALONG_MOTORWAY | 6 | none |



## PowerType {#powertype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| POWER_TYPE_UNSPECIFIED | 0 | none |

| POWER_TYPE_AC_1_PHASE | 1 | none |

| POWER_TYPE_AC_2_PHASE | 2 | none |

| POWER_TYPE_AC_2_PHASE_SPLIT | 3 | none |

| POWER_TYPE_AC_3_PHASE | 4 | none |

| POWER_TYPE_DC | 5 | none |



## ReservationRestrictionType {#reservationrestrictiontype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| RESERVATION_RESTRICTION_TYPE_UNSPECIFIED | 0 | none |

| RESERVATION_RESTRICTION_TYPE_RESERVATION | 1 | none |

| RESERVATION_RESTRICTION_TYPE_RESERVATION_EXPIRES | 2 | none |



## Status {#status}

| Name | Number | Description |
| ---- | ------ | ----------- |

| STATUS_UNSPECIFIED | 0 | none |

| STATUS_AVAILABLE | 1 | none |

| STATUS_BLOCKED | 2 | none |

| STATUS_CHARGING | 3 | none |

| STATUS_INOPERATIVE | 4 | none |

| STATUS_OUT_OF_ORDER | 5 | none |

| STATUS_PLANNED | 6 | none |

| STATUS_REMOVED | 7 | none |

| STATUS_RESERVED | 8 | none |

| STATUS_UNKNOWN | 9 | none |



## TariffDimensionType {#tariffdimensiontype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| TARIFF_DIMENSION_TYPE_UNSPECIFIED | 0 | none |

| TARIFF_DIMENSION_TYPE_ENERGY | 1 | none |

| TARIFF_DIMENSION_TYPE_FLAT | 2 | none |

| TARIFF_DIMENSION_TYPE_PARKING_TIME | 3 | none |

| TARIFF_DIMENSION_TYPE_TIME | 4 | none |



## TariffType {#tarifftype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| TARIFF_TYPE_UNSPECIFIED | 0 | none |

| TARIFF_TYPE_AD_HOC_PAYMENT | 1 | none |

| TARIFF_TYPE_PROFILE_CHEAP | 2 | none |

| TARIFF_TYPE_PROFILE_FAST | 3 | none |

| TARIFF_TYPE_REGULAR | 4 | none |

| TARIFF_TYPE_PROFILE_GREEN | 5 | none |



## TokenType {#tokentype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| TOKEN_TYPE_UNSPECIFIED | 0 | none |

| TOKEN_TYPE_APP_USER | 1 | none |

| TOKEN_TYPE_OTHER | 2 | none |

| TOKEN_TYPE_RFID | 3 | none |

| TOKEN_TYPE_AD_HOC_USER | 4 | none |



## EvAccessType {#evaccesstype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| EV_ACCESS_TYPE_UNSPECIFIED | 0 | none |

| EV_ACCESS_TYPE_PUBLIC | 1 | none |

| EV_ACCESS_TYPE_PRIVATE | 2 | none |

## EvCapabilities {#evcapabilities}

| Name | Number | Description |
| ---- | ------ | ----------- |

| EV_CAPABILITIES_UNSPECIFIED | 0 | none |

| EV_CAPABILITIES_CHARGING_PROFILE_CAPABLE | 1 | none |

| EV_CAPABILITIES_CREDIT_CARD_PAYABLE | 2 | none |

| EV_CAPABILITIES_REMOTE_START_STOP_CAPABLE | 3 | none |

| EV_CAPABILITIES_RESERVABLE | 4 | none |

| EV_CAPABILITIES_RFID_READER | 5 | none |

| EV_CAPABILITIES_UNLOCK_CAPABLE | 6 | none |

## EvChargersFeature {#evchargersfeature}

| Name | Number | Description |
| ---- | ------ | ----------- |

| EV_CHARGERS_FEATURE_UNSPECIFIED | 0 | none |

| EV_CHARGERS_FEATURE_IN_STLA_NETWORK | 1 | none |

| EV_CHARGERS_FEATURE_PLUG_AND_CHARGE | 2 | none |

## EvChargersPaymentMethod {#evchargerspaymentmethod}

| Name | Number | Description |
| ---- | ------ | ----------- |

| EV_CHARGERS_PAYMENT_METHOD_UNSPECIFIED | 0 | none |

| EV_CHARGERS_PAYMENT_METHOD_CREDIT_CARD | 1 | none |

| EV_CHARGERS_PAYMENT_METHOD_DEBIT_CARD | 2 | none |

| EV_CHARGERS_PAYMENT_METHOD_RFID_CARD | 3 | none |

| EV_CHARGERS_PAYMENT_METHOD_MOBILE_APPLICATION | 4 | none |

## EvConnectorFormat {#evconnectorformat}

| Name | Number | Description |
| ---- | ------ | ----------- |

| EV_CONNECTOR_FORMAT_UNSPECIFIED | 0 | none |

| EV_CONNECTOR_FORMAT_SOCKET | 1 | none |

| EV_CONNECTOR_FORMAT_CABLE | 2 | none |

## EvConnectorType {#evconnectortype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| EV_CONNECTOR_TYPE_UNSPECIFIED | 0 | none |

| EV_CONNECTOR_TYPE_CHADEMO | 1 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_A | 2 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_B | 3 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_C | 4 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_D | 5 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_E | 6 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_F | 7 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_G | 8 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_H | 9 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_I | 10 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_J | 11 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_K | 12 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_L | 13 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_M | 14 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_N | 15 | none |

| EV_CONNECTOR_TYPE_DOMESTIC_O | 16 | none |

| EV_CONNECTOR_TYPE_GBT_AC | 17 | none |

| EV_CONNECTOR_TYPE_GBT_DC | 18 | none |

| EV_CONNECTOR_TYPE_IEC_60309_2_SINGLE_16 | 19 | none |

| EV_CONNECTOR_TYPE_IEC_60309_2_THREE_16 | 20 | none |

| EV_CONNECTOR_TYPE_IEC_60309_2_THREE_32 | 21 | none |

| EV_CONNECTOR_TYPE_IEC_60309_2_THREE_64 | 22 | none |

| EV_CONNECTOR_TYPE_IEC_62196_T1 | 23 | none |

| EV_CONNECTOR_TYPE_IEC_62196_T1_COMBO | 24 | none |

| EV_CONNECTOR_TYPE_IEC_62196_T2 | 25 | none |

| EV_CONNECTOR_TYPE_IEC_62196_T2_COMBO | 26 | none |

| EV_CONNECTOR_TYPE_IEC_62196_T3A | 27 | none |

| EV_CONNECTOR_TYPE_IEC_62196_T3C | 28 | none |

| EV_CONNECTOR_TYPE_NEMA_5_20 | 29 | none |

| EV_CONNECTOR_TYPE_NEMA_6_30 | 30 | none |

| EV_CONNECTOR_TYPE_NEMA_10_30 | 31 | none |

| EV_CONNECTOR_TYPE_NEMA_10_50 | 32 | none |

| EV_CONNECTOR_TYPE_NEMA_14_30 | 33 | none |

| EV_CONNECTOR_TYPE_NEMA_14_50 | 34 | none |

| EV_CONNECTOR_TYPE_PANTOGRAPH_BOTTOM_UP | 35 | none |

| EV_CONNECTOR_TYPE_PANTOGRAPH_BOTTOM_DOWN | 36 | none |

| EV_CONNECTOR_TYPE_TESLA_R | 37 | none |

| EV_CONNECTOR_TYPE_TESLA_S | 38 | none |

## EvPowerType {#evpowertype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| EV_POWER_TYPE_UNSPECIFIED | 0 | none |

| EV_POWER_TYPE_AC_1_PHASE | 1 | none |

| EV_POWER_TYPE_AC_3_PHASE | 2 | none |

| EV_POWER_TYPE_DC | 3 | none |

## EvStatus {#evstatus}

| Name | Number | Description |
| ---- | ------ | ----------- |

| EV_STATUS_UNSPECIFIED | 0 | none |

| EV_STATUS_AVAILABLE | 1 | none |

| EV_STATUS_BLOCKED | 2 | none |

| EV_STATUS_CHARGING | 3 | none |

| EV_STATUS_INOPERATIVE | 4 | none |

| EV_STATUS_OUT_OF_ORDER | 5 | none |

| EV_STATUS_PLANNED | 6 | none |

| EV_STATUS_REMOVED | 7 | none |

| EV_STATUS_RESERVED | 8 | none |

| EV_STATUS_UNKNOWN | 9 | none |













































## Fee {#fee}

| Name | Number | Description |
| ---- | ------ | ----------- |

| FEE_UNSPECIFIED | 0 | none |

| FREE | 1 | none |

| PAID | 2 | none |

## ParkingType {#parkingtype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| PARKING_TYPE_UNSPECIFIED | 0 | none |

| PARKING_TYPE_PUBLIC | 1 | none |

| PARKING_TYPE_STADIUM | 2 | none |

| PARKING_TYPE_AIRPORT | 3 | none |

| PARKING_TYPE_EVENT | 4 | none |

| PARKING_TYPE_STREET | 5 | none |

| PARKING_TYPE_CARPOOL | 6 | none |







## FuelType {#fueltype}

| Name | Number | Description |
| ---- | ------ | ----------- |

| FUEL_TYPE_UNSPECIFIED | 0 | none |

| FUEL_TYPE_DIESEL | 1 | none |

| FUEL_TYPE_GASOLINE | 2 | none |

| FUEL_TYPE_CNG | 3 | none |

| FUEL_TYPE_LPG | 4 | none |

| FUEL_TYPE_HYDROGEN | 5 | none |

## PriceLevel {#pricelevel}

| Name | Number | Description |
| ---- | ------ | ----------- |

| PRICE_LEVEL_UNSPECIFIED | 0 | none |

| PRICE_LEVEL_FREE | 1 | none |

| PRICE_LEVEL_INEXPENSIVE | 2 | none |

| PRICE_LEVEL_MODERATE | 3 | none |

| PRICE_LEVEL_EXPENSIVE | 4 | none |

| PRICE_LEVEL_VERY_EXPENSIVE | 5 | none |

## SortingRankBias {#sortingrankbias}

| Name | Number | Description |
| ---- | ------ | ----------- |

| SORTING_RANK_BIAS_UNSPECIFIED | 0 | none |

| SORTING_RANK_BIAS_DISTANCE | 1 | SORTING_RANK_BIAS_RELEVANCE = 2; |










# Scalar Value Types

| .proto Type | Notes | C++ Type | Java Type | Python Type |
| ----------- | ----- | -------- | --------- | ----------- |
| <div><h4 id="double" /></div><a name="double" /> double |  | double | double | float |
| <div><h4 id="float" /></div><a name="float" /> float |  | float | float | float |
| <div><h4 id="int32" /></div><a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int |
| <div><h4 id="int64" /></div><a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long |
| <div><h4 id="uint32" /></div><a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long |
| <div><h4 id="uint64" /></div><a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long |
| <div><h4 id="sint32" /></div><a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int |
| <div><h4 id="sint64" /></div><a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long |
| <div><h4 id="fixed32" /></div><a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int |
| <div><h4 id="fixed64" /></div><a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long |
| <div><h4 id="sfixed32" /></div><a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int |
| <div><h4 id="sfixed64" /></div><a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long |
| <div><h4 id="bool" /></div><a name="bool" /> bool |  | bool | boolean | boolean |
| <div><h4 id="string" /></div><a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode |
| <div><h4 id="bytes" /></div><a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str |

