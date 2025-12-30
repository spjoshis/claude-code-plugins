---
name: performance-testing
description: Master performance testing with load testing, stress testing, JMeter, k6, and performance benchmarking.
---

# Performance Testing

Conduct performance testing to ensure applications meet scalability, responsiveness, and stability requirements under load.

## When to Use This Skill

- Load testing
- Stress testing
- Scalability validation
- Performance benchmarking
- Capacity planning
- Performance regression testing
- SLA validation
- Bottleneck identification

## Core Concepts

### 1. k6 Load Test Script

```javascript
// load-test.js
import http from 'k6/http';
import { check, sleep } from 'k6';

export const options = {
  stages: [
    { duration: '2m', target: 100 }, // Ramp up to 100 users
    { duration: '5m', target: 100 }, // Stay at 100 users
    { duration: '2m', target: 200 }, // Ramp up to 200 users
    { duration: '5m', target: 200 }, // Stay at 200 users
    { duration: '2m', target: 0 },   // Ramp down to 0
  ],
  thresholds: {
    http_req_duration: ['p(95)<500'], // 95% requests < 500ms
    http_req_failed: ['rate<0.01'],   // Error rate < 1%
  },
};

export default function () {
  const res = http.get('https://api.example.com/products');
  
  check(res, {
    'status is 200': (r) => r.status === 200,
    'response time < 500ms': (r) => r.timings.duration < 500,
  });
  
  sleep(1);
}
```

### 2. Performance Test Report

```markdown
# Performance Test Report

**Test Date**: 2024-01-15
**Application**: E-Commerce API
**Tool**: k6

## Test Configuration
- Virtual Users: 100 → 200
- Duration: 16 minutes
- Ramp-up: 2 minutes per stage

## Results Summary

| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Avg Response Time | <300ms | 245ms | ✅ Pass |
| P95 Response Time | <500ms | 412ms | ✅ Pass |
| P99 Response Time | <1000ms | 876ms | ✅ Pass |
| Throughput | >100 req/s | 125 req/s | ✅ Pass |
| Error Rate | <1% | 0.3% | ✅ Pass |

## Bottlenecks Identified
1. Database queries slow at 200+ users
2. Image processing CPU-intensive

## Recommendations
1. Add database indexing on product_id
2. Implement CDN for images
3. Add caching layer (Redis)
```

## Best Practices

1. **Define objectives** - Response time, throughput, concurrent users
2. **Realistic scenarios** - Match production patterns
3. **Gradual load increase** - Ramp up slowly
4. **Monitor system** - CPU, memory, database
5. **Baseline first** - Know current performance
6. **Isolate environment** - Dedicated test environment
7. **Analyze results** - Identify bottlenecks
8. **Continuous testing** - Performance regression tests

## Resources

- **k6**: https://k6.io
- **JMeter**: https://jmeter.apache.org
- **Gatling**: https://gatling.io
