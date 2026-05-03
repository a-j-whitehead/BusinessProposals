# Proposal: Solar Farm (Spain)

**Location:** Soria, Spain  
**Capacity:** 10kWp Solar / 15kWh Battery / 40-Node Grid-Hybrid Cluster  
**Date:** May 2026

## 1. Summary

Solar Farm is a specialized high-density compute farm designed to arbitrage solar energy and repurposed hardware into high-yield decentralized cloud revenue. By operating as a grid-tied hybrid, the project captures available solar energy while maintaining 24/7 Tier-1 availability on the Akash Network.

This proposal outlines the transition to a warehouse-based model in Soria, leveraging high-altitude cooling advantages and Spanish tax incentives for a predicted payback period of 25 months.

## 2. Infrastructure & Location

- **Facility:** Rented nave industrial (warehouse) in Polígono Industrial Las Casas, Soria.
- **Connectivity:** Existing FTTH (Fiber to the Home/Business) with 1Gbps symmetric capacity.

## 3. Financial Projections (Pilot Scale)

### 3.1 Startup Costs (CapEx)

| Item | Description | Cost |
| --- | --- | ---: |
| Solar Array (10kWp) | Ground/roof ballasted + hybrid inverter (post-grant) | €8,400 |
| Battery Storage | 15kWh LFP (Lithium Iron Phosphate) stack | €5,850 |
| Compute Nodes | 32× salvaged + 4× refurbished i7 (8th Gen) | €1,000 |
| Infrastructure | DC-DC converters, 10G switches, NAS boot-server | €1,200 |
| Legal / Permitting | Industrial grid-tie authorization (Autoconsumo) | €1,500 |
| **Total CapEx** |  | **€17,950** |

### 3.2 Operating Expenses (OpEx - Monthly)

| Item | Description | Cost |
| --- | --- | ---: |
| Warehouse Rent | Industrial unit on outskirts of Soria | €450 |
| Night-Time Energy | Grid consumption (Tariff 3.0TD - off-peak) | €240 |
| Maintenance Fund | Higher salvage failure rate (15-20% vs. 8-10% baseline) | €180 |
| Connectivity | Business-grade static IP fiber | €60 |
| **Total Monthly OpEx** |  | **€930** |

### 3.3 Revenue & Profitability

| Metric | Monthly | Annual |
| --- | ---: | ---: |
| Gross Revenue | €1,650 | €19,800 |
| Net Profit | €720 | €8,640 |
| ROI / Payback | **25 months** | — |

## 4. Technical Implementation

### 4.1 Energy

The cluster uses a state-aware load balancer programmed in Python/Go to optimize energy costs:

- **09:00 - 18:00:** Solar powered (10kWp array covering daytime baseline). Surplus energy charges the 15kWh LFP battery.
- **18:00 - 22:00:** Battery discharge. Servers run on stored solar energy to avoid Spanish P1/P2 peak grid tariffs.
- **22:00 - 08:00:** Grid switchover. Cluster draws from the grid during the super-off-peak Valle period (P6).

### 4.2 Compute Strategy

We target Akash Network Standard Instances. By maintaining 24/7 uptime through the grid-tie, we qualify for a Quality of Service (QoS) score >95%, enabling bids on high-priority Docker containers and AI inference endpoints rather than low-value spot rendering.

### 4.3 Hybrid Salvage + Refurbished Hardware Model

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
- Maintenance fund increased to €180/month to account for higher replacement cycles
- Grid-tie architecture provides seamless failover without service interruption

## 5. Risk Mitigation & Tax Strategy

- **E-Waste Sourcing Risk:** Partnered with certified Spanish e-waste recyclers and industrial surplus auctions. 60-70% viability rate built into sourcing model. Initial batch testing (24-72 hour burn-in) identifies unreliable units before deployment to maintain QoS.
- **Hardware Heterogeneity:** Tiered node architecture uses anchor (refurbished) nodes for critical services and salvaged nodes for batch/background workloads, reducing QoS variance.
- **Thermal Consistency:** Using the grid-tie eliminates daily thermal cycling (on/off stress), extending node lifespan from about 2 years to roughly 4 years. Passive cooling + high-altitude airflow compensate for older hardware thermal signatures.
- **Tax Optimization:** Under Royal Decree-Law 7/2026, the project qualifies for Freedom of Amortization. 100% of the €17,950 investment can be depreciated in Year 1, significantly offsetting corporate tax. E-waste sourcing costs are deductible as materials; labor can be expensed as consulting.
- **Scalability:** The warehouse model supports modular expansion. Each subsequent rack benefits from proven salvage sourcing channels and shared infrastructure, further lowering per-node CapEx.

## 6. Conclusion

The Soria Hybrid model represents an economically realistic version of green compute. By combining salvaged e-waste hardware with a small cohort of refurbished anchor nodes, the project manages CapEx while investing in necessary QA. The hybrid architecture mitigates reliability risk through tiered workload allocation, while the grid-tie topology provides thermal and operational advantages regardless of node vintage.

This model demonstrates that circular economy sourcing is compatible with cloud-grade QoS standards. The combination of e-waste arbitrage, high-altitude cooling, and Spanish energy subsidies creates a defensible margin against traditional cloud providers while advancing environmental sustainability.

There may be options to further reduce costs. I would like to explore setting up some volunteer, or similar, groups to salvage compute on the basis that it is eco friendly. I think I have friends and family that may be interested.

## Resources
* https://akash.network/pricing/provider-calculator/
* https://www.wired.com/story/how-to-build-a-pc/
* https://www.reddit.com/r/buildapc/comments/5edfki/building_junkyard_rigs_for_fun_and_profit_a/
* https://drive.google.com/file/d/1MJKt9iSFPtYvTrQKjxbyUxyQv1jC7SWL/view
* https://www.wired.com/story/how-to-build-a-pc/
