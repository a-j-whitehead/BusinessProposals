# Business Proposal: Galicia Wind Farm (Stage 3 Hybrid)

**Location:** Galicia, Northwest Spain (Vigo or A Coruña Industrial Zones)  
**Capacity:** 10kW Wind Turbine / 10kWh Battery / 40-Node Grid-Hybrid Cluster  
**Date:** May 2026

## 1. Executive Summary

The Galicia Wind Farm is a specialized high-density compute farm designed to arbitrage coastal wind energy and repurposed hardware into high-yield decentralized cloud revenue. By operating as a grid-tied hybrid in Spain's premier wind region, the project captures 100% of available wind energy while maintaining 24/7 Tier-1 availability on the Akash Network.

This proposal outlines deployment to an industrial zone in Galicia, leveraging tier-1 European wind resources and transitions the project from arbitrage-dependent tariff optimization to net energy exporter status. Predicted payback period: 18 months with significantly improved long-term margins.

## 2. Infrastructure & Location

- **Facility:** Rented nave industrial (warehouse) in industrial zone near Vigo or A Coruña, Galicia.
- **Wind Resource:** Atlantic coastal exposure provides 9.5-11 m/s average, 35-40% capacity factor (tier-1 European wind).
- **Cooling Strategy:** Coastal mild ambient temperatures; modest cooling requirements compared to high-altitude solar sites.
- **Connectivity:** 1Gbps+ FTTH available in major Galician industrial zones; strong fiber infrastructure.
- **Regulatory Environment:** Mature wind permitting infrastructure; REE (Spanish National Grid) contracts available; Autoconsumo industrial grid-tie authorization streamlined for wind operations.

## 3. Financial Projections (Pilot Scale)

### 3.1 Startup Costs (CapEx)

| Item | Description | Cost |
| --- | --- | ---: |
| Wind Turbine (10kW) | Horizontal-axis, industrial-grade + grid-tie inverter | €8,500 |
| Battery Storage | 10kWh LFP (Lithium Iron Phosphate) stack | €3,900 |
| Compute Nodes | 32× salvaged + 4-8× refurbished i7 (8th Gen) | €1,000 |
| Salvage Labor | Teardown, testing, reassembly (~60-120 hours) | €600 |
| Infrastructure | DC-DC converters, 10G switches, NAS boot-server | €1,200 |
| Turbine Installation | Structural assessment, mast, foundation | €3,000 |
| Legal / Permitting | Industrial grid-tie authorization + wind permits | €2,500 |
| **Total CapEx** |  | **€20,700** |

### 3.2 Operating Expenses (OpEx - Monthly)

| Item | Description | Cost |
| --- | --- | ---: |
| Warehouse Rent | Industrial unit in Galician industrial zone | €700 |
| Night-Time Grid (rare) | Minimal usage; mostly self-powered or exporting | €20 |
| Maintenance Fund | Higher salvage failure rate + turbine upkeep | €200 |
| Turbine Service (annually amortized) | Blade inspection, bearing maintenance | €100 |
| Connectivity | Business-grade static IP fiber | €60 |
| **Total Monthly OpEx** |  | **€1,080** |

### 3.3 Revenue & Profitability

| Metric | Monthly | Annual | Change vs. Soria Solar |
| --- | ---: | ---: | ---: |
| Gross Revenue | €2,400 | €28,800 | +€9,000 (+45%) |
| Net Profit | €1,320 | €15,840 | +€3,600 (+29%) |
| ROI / Payback | **18 months** | — | +2 months (offset by stability) |
| Grid Independence | ~120% (net exporter) | — | Unlimited |

## 4. Technical Implementation

### 4.1 Wind Energy Generation (Galicia Advantage)

**Wind Profile:**
- Atlantic coastal exposure (fetch from open ocean)
- Average wind speed: 10 m/s (compared to 4.8 m/s in Soria)
- Annual capacity factor: 35-40% (vs. ~15% for solar-equivalent regions)
- Consistent year-round generation (winter peaks, summer lows, but no seasonal collapse)

**10kW Turbine Performance:**
- Annual output: ~31,500 kWh
- Daily average: ~86 kWh (vs. Soria solar's 17 kWh)
- Seasonal variation: ±15% (minimal compared to solar's ±40%)

### 4.2 The "Galicia Loop" (Energy Logic)

The cluster uses a state-aware load balancer programmed in Python/Go to optimize energy costs and maximize export revenue:

- **Daytime/Windy periods:** 100% wind powered. Surplus energy charges 10kWh LFP battery and/or exports to grid at peak tariff rates.
- **Low-wind periods:** Battery discharge covers compute workloads (3-4 hours autonomous runtime).
- **Calm/night periods (rare, ~10% of year):** Grid draws from off-peak tariffs or operates at reduced capacity.

**Grid Export Advantage:**
- Galicia benefits from Régimen Económico Complementario (REC) wind subsidies
- Self-consumption surplus sells back to REE at commercially advantageous rates
- Eliminates need for tariff arbitrage; revenue stream independent of grid pricing

### 4.3 Compute Strategy

We target Akash Network Standard & Premium Instances. By maintaining 24/7 uptime through consistent wind generation, we qualify for a Quality of Service (QoS) score >95%, enabling bids on high-priority Docker containers, AI inference endpoints, and persistent compute jobs rather than low-value spot rendering.

Wind's consistency (vs. solar's diurnal variation) provides more stable QoS maintenance throughout annual cycles.

### 4.4 Hybrid Salvage + Refurbished Hardware Model

**Architecture:**
- **32 salvaged nodes (85%):** i7-8th Gen CPUs extracted from e-waste corporate surplus and manufacturer scrap yards
- **4-8 anchor nodes (15-20%):** Pre-tested refurbished mini-PCs from certified refurb suppliers (hedge against higher failure rates)

**Sourcing & Assembly:**
1. Source 60-65 used systems from Spanish e-waste recyclers (€5-10/unit)
2. Extract and stress-test CPU/RAM/SSD modules (24-72 hour burn-in per batch)
3. Assemble into compact mini-ITX configurations or DIY 3U rackmount enclosures (€30-50/chassis)
4. Expected viability: 60-70% of sourced units → 40 production-ready nodes

**Reliability Mitigation:**
- Salvaged nodes exhibit 15-20% annual failure rate (vs. 8-10% for new refurb)
- Anchor nodes provide QoS stability buffer; salvaged nodes handle non-critical background workloads
- Maintenance fund increased to €200/month to account for higher replacement cycles
- Consistent grid-tie architecture provides seamless failover without service interruption

## 5. Risk Mitigation & Tax Strategy

- **Wind Resource Validation:** Galicia's wind data is extensively documented by Spain's Instituto Geográfico Nacional and validated by REE. Industrial wind operations in region boast industry-standard 95%+ accuracy in capacity factor predictions.
- **Hardware Heterogeneity:** Tiered node architecture uses anchor (refurbished) nodes for critical services and salvaged nodes for batch/background workloads, reducing variance in QoS.
- **Turbine Maintenance:** 10kW turbine maintenance follows industry standards; bearing service ~€1,200/year, blade inspection ~€500/year. Coastal setting (salt spray) increases preventative maintenance cost but remains within budget.
- **Tax Optimization:** Under Royal Decree-Law 7/2026, the project qualifies for Freedom of Amortization. 100% of the €20,700 investment can be depreciated in Year 1, significantly offsetting corporate tax. Wind infrastructure components may qualify for additional accelerated depreciation schedules.
- **Grid Export Revenue:** Surplus wind generation yields additional revenue through REE grid export contracts (~€1,500-2,000/year estimated as exports grow). This stream is independent of Akash Network revenue, providing diversification.
- **Scalability:** The warehouse model supports modular 10kW expansion. Each additional turbine benefits from shared grid interconnect, NAS, and networking infrastructure, lowering per-unit CapEx. Multi-turbine sites can achieve economies of scale.

## 6. Comparison: Wind vs. Solar (Galicia Context)

| Factor | Wind (Proposed) | Solar Alternative |
| --- | --- | --- |
| **Generation** | 31,500 kWh/year | 7,000 kWh/year (if solar in Galicia) |
| **Upfront CapEx** | €20,700 | €11,900 |
| **Annual Revenue** | €28,800 | €8,400 |
| **Payback** | 18 months | 16 months |
| **Annual Profit** | €15,840 | €7,560 |
| **Wind/Solar Suitability** | Tier-1 (excellent) | Tier-2 (moderate) |
| **Seasonal Stability** | High (consistent) | Low (diurnal + seasonal variation) |

**Why wind wins in Galicia:** While solar has lower upfront cost and faster initial payback, Galicia's wind resource is world-class. Wind generation is 4.5× higher annually; the +2 month payback penalty is offset by superior annual margins (€8,280/year advantage).

## 7. Conclusion

The Galicia Wind Farm represents the optimal deployment of green compute infrastructure for northwest Spain. By shifting from grid-dependent tariff arbitrage (Soria solar model) to consistent wind generation with grid export capabilities, the project achieves:

- **Higher annual revenue** (€28,800 vs. €19,800 solar-only)
- **Net energy exporter status** (eliminates grid dependency)
- **Defensible long-term margins** (wind is commoditized, predictable infrastructure)
- **Regulatory clarity** (Spain's REE framework is mature for wind operations)
- **Scalable deployment template** (multi-turbine sites reduce per-unit costs)

The combination of Galicia's tier-1 wind resources, proven industrial permitting infrastructure, and stable grid export revenue creates a resilient foundation for decentralized cloud compute at scale. The 18-month payback window and 29% profit advantage over solar-based alternatives justify the modest CapEx increase.

**Recommended next phase:** Site assessment in specific Galician zones (Polígono Industrial A Grixoa, Vigo or Zona Industrial As Somozas, A Coruña) to validate wind resource and secure warehouse lease.
