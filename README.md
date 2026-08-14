<script>

document.getElementById("bookingForm").addEventListener("submit", function(event) {

  event.preventDefault();

  const booking = {

    id: Date.now(),

    name: document.getElementById("name").value,

    phone: document.getElementById("phone").value,

    service: document.getElementById("service").value,

    date: document.getElementById("date").value,

    time: document.getElementById("time").value,

    address: document.getElementById("address").value,

    status: "Pending"

  };

  const bookings =
    JSON.parse(localStorage.getItem("carWashBookings")) || [];

  bookings.push(booking);

  localStorage.setItem(
    "carWashBookings",
    JSON.stringify(bookings)
  );

  alert(
    "Booking Successfully Received! 🚗\n\n" +
    "Thank you, " + booking.name + "!"
  );

  document.getElementById("bookingForm").reset();

});

</script>
