# State Estimation {#stateestimation status=ready}

The Duckiedrone includes three approaches for low-level state
estimation (velocity and integrated position).  The default state
estimator is the Exponential Moving Average, which simply maintains a
moving average across different sensor estimates.  We have also
implemented several variants of an Unscented Kalman Filter, which uses
a control input and a measurement input to enable the estimator to
smooth sensor measurements while also updating quickly when the drone
changes state.

To see options for the state estimator, run `python state_estimator.py
--help`.  You can also read more about the Unscented Kalman Filter in
the Duckiesky Learning Materials chapter on this topic.

When the UKF is working you can see a graph appear in the web
interface along with the raw sensor value for the height.

<img src="ukf.png" width="400" alt="Graph of the UKF reading with the raw sensor value."/>
