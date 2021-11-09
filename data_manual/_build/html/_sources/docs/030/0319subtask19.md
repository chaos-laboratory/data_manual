# Visualise with Grafana

1. To check the data, go to <a href="https://andlchaos300l.princeton.edu:3000" target="_blank">https://andlchaos300l.princeton.edu:3000</a>, make sure you are logged into the Princeton VPN or on Princeton Campus. Login with our Chaos Lab Grafana Login. Approach out lab member for login details.

2. At the Grafana homepage, go to + sign at the sidebar. Create -> Dashboard -> Add New Panel. At the Query bar. Specify Things = $the name of your particle device$, Datastream = $datastream to visualise$. You will be able to see the data. Set the refresh rate to very 5s. The visualised data might look alittle messy at first. But it will smoothen after a few hours. It is a bug with the sensorthings api plugin for Grafana. Repeat Add Panel for all the other datastreams you like to visualise.
    ```{figure} /_static/0319subtask19/grafana.png
    :width: 100%
    :name: grafana
    Visualization of data in Grafana
    ```
3. You can reduce the messiness by switching off the lines display and only turning on the points display.
    ```{figure} /_static/0319subtask19/grafana_display.png
    :width: 50%
    ```

4. If you are unable to hover on the latest points. You can change the following hover tip settings to improve the situation.
    ```{figure} /_static/0319subtask19/grafana_display1.png
    :width: 80%
    ```
5. To download the data as CSV from Grafana.
    - Click on the Stat icon.
    ```{figure} /_static/0319subtask19/grafana_display2.png
    :width: 80%
    ```
    - Click on the field tab. Change the decimal to the number desired number of decimal places.
    ```{figure} /_static/0319subtask19/grafana_display3.png
    :width: 80%
    ```
    - Choose the time range to download.
    ```{figure} /_static/0319subtask19/grafana_display4.png
    :width: 100%
    ```
    - Click on the Graph Title -> Inspect -> Data.
    ```{figure} /_static/0319subtask19/grafana_display5.png
    :width: 100%
    ```
    - You will be able to download the data to CSV. For more advance analytics, please refer to the Advance Analytics task {doc}`../030/0312advance_analytics`.
    ```{figure} /_static/0319subtask19/grafana2.png
    :width: 100%
    ```
