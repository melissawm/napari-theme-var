# Meeting schedule

We hold regular meetings, the timings of which are available on our [public calendar](https://calendar.google.com/calendar/embed?src=c_35r93ec6vtp8smhm7dv5uot0v4%40group.calendar.google.com).

If you are using napari or interested in how napari could be used in your work, please join one of our regular community meetings. If you're interested in diving deep on particular topic you could join the closest working group meeting. We currently have four working groups 'Bundled Application', 'Plugins', 'Architecture', and 'Documentation' that meet on a semi-regular candence. You can learn more about our working groups and community meetings in the corresponding discussion streams on the [napari Zulip](https://napari.zulipchat.com/login/).

<div id='community_calendar'></div>

<div id='timezone'></div>

<script src='https://cdn.jsdelivr.net/npm/fullcalendar@6.1.9/index.global.min.js'></script>
<script src="https://cdn.jsdelivr.net/npm/@fullcalendar/google-calendar@6.1.9/index.global.min.js"></script>
<script>
  document.getElementById('timezone').innerHTML = "All times shown in "+Intl.DateTimeFormat().resolvedOptions().timeZone+".";
  document.addEventListener('DOMContentLoaded', function () {
    var community_calendar = document.getElementById('community_calendar');
    var calendar = new FullCalendar.Calendar(community_calendar,
    {
      height: 650,
      timeZone: 'local',
      initialView: 'dayGridMonth',
      headerToolbar: {
        left: "prev,next today",
        center: "title",
        right: "dayGridMonth,listWeek",
      },
      googleCalendarApiKey: api_key,
      events: {
          googleCalendarId: 'c_35r93ec6vtp8smhm7dv5uot0v4@group.calendar.google.com',
      },
      eventClick: function (info) {
        info.jsEvent.preventDefault();
        var eventObj = info.event;
        alert(
          'Event: ' + eventObj.title + '\n\n'
          + 'Description: ' + eventObj.extendedProps.description + '\n\n'
          + 'URL: ' + eventObj.url);
      },
      eventDisplay: 'block',
    });
    calendar.render();
  });
</script>