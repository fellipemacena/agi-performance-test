# Performance Test

## Objective
Evaluate the system behavior under different load patterns using Apache JMeter.

## Scenarios

### Load Test
- ~250 users
- Gradual ramp-up
- Duration: ~60 seconds

### Spike Test
- ~300 users
- Fast ramp-up
- Duration: ~30 seconds

## Test Flow

1. GET Home
2. POST Search Flights
3. POST Select Flight
4. POST Confirm Flight

## Strategy

- Transaction Controller used to measure full flow execution
- "Stop Thread" strategy applied to avoid cascading failures
- Fixed data used for flight selection (no correlation implemented)

## Results

### Load Test
- Stable response time
- Low error rate
- Consistent throughput

### Spike Test
- Increased response time
- Higher variability
- Signs of performance degradation under sudden load

## Execution

Run with:

jmeter -n -t agi-performance-test.jmx -l resultado.jtl
