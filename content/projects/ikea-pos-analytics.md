---
title: "IKEA Breda POS Terminal Deployment Analytics Dashboard"
date: 2024-11-16T10:00:00+02:00
draft: false
author: "Szymon"
startDate: "Nov 2024"
endDate: "Nov 2024"
tags:
  - Power BI
  - Business Analytics
  - Data Visualization
  - DAX
image: /images/projects/ikea.png
description: "Analytics dashboard tracking POS terminal deployments, identifying operational patterns and compliance issues for IKEA Breda"
presentationLink: "/files/ikea-powerbi.pdf"
---

## Project Overview

This project demonstrates the power of business analytics in optimizing retail operations. I developed a comprehensive Power BI dashboard for IKEA Breda that analyzes the deployment lifecycle of POS (Point-of-Sale) terminals across the store.

The dashboard transforms raw operational data from June to August 2024 into actionable insights, enabling the team to identify deployment patterns, track compliance, and detect operational anomalies. This project showcases my ability to bridge technical data engineering with strategic business decision-making.

## Business Context

IKEA Breda manages a complex network of POS terminals deployed across multiple departments and checkout locations. Effective terminal management requires:

- **Tracking terminal lifecycle**: From initial deployment to re-deployment and management
- **Monitoring compliance**: Ensuring terminals meet operational standards
- **Identifying inefficiencies**: Detecting gaps and delays in the deployment process
- **Performance analysis**: Understanding deployment patterns and patterns across locations
- **Operational optimization**: Improving processes based on data-driven insights

## Key Findings from Analysis

### Overview Metrics (Jun 3 - Aug 30, 2024)

**Total Deployments**: 1,337 deployment events across the period
**Terminals Tracked**: 67 unique terminals analyzed
**Average Time Gap**: -2.35 minutes between deployments (indicating some retroactive logging)
**Overall Compliance Rate**: 92.15%

### Deployment Frequency Analysis

**Monthly Breakdown**:
- **June 2024**: ~480 deployments
- **July 2024**: ~460 deployments  
- **August 2024**: ~440 deployments

*Finding*: Steady decline in deployment frequency month-over-month, suggesting stabilization of terminal placement after initial setup phase.

**Terminal Activity Distribution**:
- Maximum deployments per terminal: 48
- Most frequent deployment cycle: 2.59-2.68 minutes average time gap
- Standard deployment terminals show consistent 2-3 minute intervals

### Time Gap Analysis - Critical Insights

**Distribution of Time Differences**:
- **Normal range**: 0.5 - 3 minutes (majority of terminals)
- **Negative anomalies**: Several terminals showing -1K to -5K minute gaps
  - *Example*: Terminal 403-70007 shows -236.44 minute gap (indicating data entry issues or system timestamp problems)
  - *Example*: Kiosk 7 shows -258.19 minute gap (significant operational concern)

*Recommendation*: Investigate data integrity for terminals with extreme negative time gaps. Likely causes: system clock issues, backdated deployments, or data entry errors.

**Monthly Time Gap Trend**:
- July 2024: Average -40 to -60 minutes (indicates systematic delay or logging issue)
- August 2024: Average improving toward 0-20 minutes (positive operational improvement)

*Finding*: Time gap performance improved in August, suggesting corrective actions or system adjustments had positive effect.

### Location-Based Performance

**Best Performing Locations** (consistent 2.5+ minute intervals):
- Eco 1 (Ret 7): 2.78 min average
- Kiosk 1: 2.68 min average
- Kiosk 3: 2.67 min average
- Kiosk 2: 2.66 min average
- Kiosk 4: 2.66 min average

**Problem Areas** (anomalous time gaps):
- Kiosk 7: -258.19 minutes (critical attention needed)
- Ret 5 (Eco 9): -17.14 minutes (significant delay)
- HFB 1-3 (Food service areas): 0.00 - 0.76 minute gaps (unusually short intervals, different operational pattern)

*Insight*: Food service areas (HFB, FOO) show drastically different deployment patterns (0.5-1.5 min) compared to retail areas (2.5-2.7 min), suggesting different operational workflows or staffing patterns.

### Compliance Analysis

**Overall Compliance Rate**: 92.15%
**Compliant Weeks**: 100% compliance achieved in certain weeks (showing operational capability)
**Non-Compliant Terminals**: 10 terminals with non-compliance weeks identified
  - 403-90009, 403-100011, 403-30004 through 403-30006, 403-70007, 403-76030, 403-77031, 403-78032, 403-80008

**Terminals with Perfect Record**: Several terminals maintained 100% compliance throughout the period

*Finding*: 8% compliance gap (7.85% non-compliance rate) requires investigation. Non-compliance clustered around specific terminal models and locations.

## Technical Implementation

### Dashboard Pages

**Page 1: Overview Dashboard**
- 1,337 total deployments tracked
- 67 active terminals monitored
- -2.35 minute average time gap (aggregated across all terminals)
- Real-time KPI indicators

**Page 2: Deployment Frequency Analysis**
- Monthly deployment trends (June 480 → July 460 → Aug 440)
- Per-terminal deployment counts (max 48 deployments)
- Deployment distribution visualization

**Page 3: Time Gap Analysis**
- Histogram of time difference distribution (-6K to 0 minute range)
- Time gap trend over months (July improving to August)
- Anomaly detection highlighting problematic terminals

**Page 4: Location-Based Analysis**
- 30+ locations tracked across retail, kiosk, and food service areas
- Location average time gap comparison
- Operational pattern differences between location types

**Page 5: Compliance Overview**
- Weekly compliance rate visualization
- Terminal-specific compliance scores
- Compliance trend over weeks 22-36 (June-August)
- Non-compliant terminal identification

### Technologies Used

**Data Analytics**: Power BI Desktop, Power Query
**Programming**: DAX for advanced calculations
**Visualization**: Power BI native visuals with conditional formatting


### Strategic Insights

**Positive Trend**: Month-over-month improvement in time gap performance (July → August)
- Suggests corrective measures are working
- Maintain current operational adjustments
- Document successful process changes

**Capacity Planning**: Declining monthly deployments
- June: 480 → August: 440 (-8% decline)
- Indicates completion of terminal refresh cycle or changed operational needs
- Plan staffing and resources based on stabilized deployment levels

## Impact & Results

The dashboard enables IKEA Breda operations to:
- **Visualize operational patterns** across 67+ terminals in real-time
- **Identify compliance issues** before they escalate
- **Detect anomalies** in deployment processes automatically
- **Optimize location-specific operations** based on data insights
- **Monitor improvement trends** from month to month

## Conclusion

This Power BI dashboard successfully transformed complex operational data (1,337+ deployment events across multiple locations) into clear, actionable business intelligence. The analysis revealed both operational strengths (92.15% compliance rate, consistent deployment patterns in most locations) and areas requiring attention (negative time gaps, food service operational differences, non-compliant terminals).

By continuing to monitor these metrics and implementing the recommended actions, IKEA Breda can further optimize POS terminal management, improve compliance rates, and reduce operational inefficiencies.
