<script>
  let formData = {
    name: '',
    email: '',
    phone: '',
    date: '',
    time: '',
    persons: ''
  }

  let submitted = false
  let errorMessage = ''

  const timeSlots = [
    '11:00 AM', '11:30 AM', '12:00 PM', '12:30 PM',
    '1:00 PM', '1:30 PM', '2:00 PM', '2:30 PM',
    '5:00 PM', '5:30 PM', '6:00 PM', '6:30 PM',
    '7:00 PM', '7:30 PM', '8:00 PM', '8:30 PM',
    '9:00 PM', '9:30 PM', '10:00 PM'
  ]

  function getMinDate() {
    const today = new Date()
    today.setDate(today.getDate() + 1)
    return today.toISOString().split('T')[0]
  }

  function getMaxDate() {
    const maxDate = new Date()
    maxDate.setDate(maxDate.getDate() + 60)
    return maxDate.toISOString().split('T')[0]
  }

  function handleSubmit(e) {
    e.preventDefault()
    errorMessage = ''

    if (!formData.name || !formData.email || !formData.phone || !formData.date || !formData.time || !formData.persons) {
      errorMessage = 'Please fill in all fields'
      return
    }

    if (formData.persons < 1 || formData.persons > 10) {
      errorMessage = 'Number of persons must be between 1 and 10'
      return
    }

    submitted = true
    setTimeout(() => {
      resetForm()
    }, 3000)
  }

  function resetForm() {
    formData = {
      name: '',
      email: '',
      phone: '',
      date: '',
      time: '',
      persons: ''
    }
    submitted = false
  }
</script>

<div class="booking-page">
  <div class="container">
    <div class="booking-wrapper">
      <h1>Book a Table</h1>
      <p class="subtitle">Reserve your table at Lee's Restaurant</p>

      {#if submitted}
        <div class="success-message">
          <h2>✓ Booking Confirmed!</h2>
          <p>Thank you, {formData.name}!</p>
          <p>Your table for {formData.persons} {formData.persons == 1 ? 'person' : 'people'} is booked for {formData.date} at {formData.time}</p>
          <p>A confirmation email has been sent to {formData.email}</p>
        </div>
      {:else}
        <form on:submit={handleSubmit} class="booking-form">
          {#if errorMessage}
            <div class="error-message">{errorMessage}</div>
          {/if}

          <div class="form-group">
            <label for="name">Full Name *</label>
            <input
              type="text"
              id="name"
              bind:value={formData.name}
              placeholder="Your full name"
              required
            />
          </div>

          <div class="form-row">
            <div class="form-group">
              <label for="email">Email Address *</label>
              <input
                type="email"
                id="email"
                bind:value={formData.email}
                placeholder="your@email.com"
                required
              />
            </div>
            <div class="form-group">
              <label for="phone">Phone Number *</label>
              <input
                type="tel"
                id="phone"
                bind:value={formData.phone}
                placeholder="(555) 123-4567"
                required
              />
            </div>
          </div>

          <div class="form-row">
            <div class="form-group">
              <label for="date">Date *</label>
              <input
                type="date"
                id="date"
                bind:value={formData.date}
                min={getMinDate()}
                max={getMaxDate()}
                required
              />
            </div>
            <div class="form-group">
              <label for="time">Time *</label>
              <select id="time" bind:value={formData.time} required>
                <option value="">Select Time</option>
                {#each timeSlots as slot}
                  <option value={slot}>{slot}</option>
                {/each}
              </select>
            </div>
          </div>

          <div class="form-group">
            <label for="persons">Number of Persons *</label>
            <div class="persons-input">
              <input
                type="number"
                id="persons"
                bind:value={formData.persons}
                min="1"
                max="10"
                placeholder="1"
                required
              />
              <span class="persons-hint">(Maximum 10 persons)</span>
            </div>
          </div>

          <button type="submit" class="submit-button">Confirm Booking</button>
        </form>
      {/if}
    </div>
  </div>
</div>

<style>
  .booking-page {
    background: linear-gradient(135deg, #f5f5f5 0%, #ffffff 100%);
    padding: 3rem 1rem;
    min-height: 80vh;
  }

  .container {
    max-width: 600px;
    margin: 0 auto;
  }

  .booking-wrapper {
    background: white;
    padding: 2.5rem;
    border-radius: 12px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.1);
  }

  h1 {
    color: #8b0000;
    text-align: center;
    margin-bottom: 0.5rem;
    font-size: 2rem;
  }

  .subtitle {
    text-align: center;
    color: #666;
    margin-bottom: 2rem;
  }

  .success-message {
    background: #d4edda;
    border: 2px solid #28a745;
    color: #155724;
    padding: 2rem;
    border-radius: 8px;
    text-align: center;
  }

  .success-message h2 {
    margin-top: 0;
    color: #155724;
  }

  .error-message {
    background: #f8d7da;
    border: 1px solid #f5c6cb;
    color: #721c24;
    padding: 0.75rem 1rem;
    border-radius: 4px;
    margin-bottom: 1.5rem;
    text-align: center;
  }

  .booking-form {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .form-group {
    display: flex;
    flex-direction: column;
  }

  .form-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }

  label {
    font-weight: 600;
    color: #333;
    margin-bottom: 0.5rem;
  }

  input,
  select {
    padding: 0.75rem;
    border: 2px solid #ddd;
    border-radius: 6px;
    font-size: 1rem;
    transition: border-color 0.3s;
    font-family: inherit;
  }

  input:focus,
  select:focus {
    outline: none;
    border-color: #8b0000;
    box-shadow: 0 0 0 3px rgba(139, 0, 0, 0.1);
  }

  .persons-input {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  .persons-hint {
    font-size: 0.85rem;
    color: #999;
  }

  .submit-button {
    background: linear-gradient(135deg, #8b0000 0%, #d90000 100%);
    color: white;
    padding: 1rem;
    border: none;
    border-radius: 6px;
    font-size: 1.1rem;
    font-weight: bold;
    cursor: pointer;
    transition: all 0.3s;
    margin-top: 0.5rem;
  }

  .submit-button:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(139, 0, 0, 0.3);
  }

  .submit-button:active {
    transform: translateY(0);
  }

  @media (max-width: 600px) {
    .booking-wrapper {
      padding: 1.5rem;
    }

    .form-row {
      grid-template-columns: 1fr;
    }

    h1 {
      font-size: 1.5rem;
    }
  }
</style>
