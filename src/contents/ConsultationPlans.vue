<template>
  <section class="bg-gray-100 py-16 px-4 sm:px-8 lg:px-16">
    <div class="max-w-7xl mx-auto text-center mb-12">
      <h2 class="text-4xl font-bold text-gray-900 mb-2">Choose Your Support Plan</h2>
      <p class="text-lg text-gray-600">No contracts. Just support when it matters most.</p>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
      <div v-for="plan in plans" :key="plan.name" :class="['rounded-xl p-6 shadow-lg border', plan.featured ? 'bg-pink-50 border-pink-500' : 'bg-white border-gray-200']">
        <h3 class="text-xl font-semibold text-gray-900 mb-2">{{ plan.name }}</h3>
        <p class="text-3xl font-bold text-gray-800 mb-4">{{ plan.price }}</p>
        <ul class="text-sm text-gray-700 mb-6 space-y-2">
          <li v-for="(feature, idx) in plan.features" :key="idx" class="flex items-start">
            <svg class="w-5 h-5 text-pink-500 mt-1 mr-2" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 00-1.414 0L9 11.586 6.707 9.293a1 1 0 00-1.414 1.414L9 14.414l8-8a1 1 0 000-1.414z" clip-rule="evenodd"/></svg>
            {{ feature }}
          </li>
        </ul>
        <button :class="['w-full py-2 rounded-md text-white font-medium', plan.featured ? 'bg-pink-600 hover:bg-pink-500' : 'bg-gray-800 hover:bg-gray-700']">
          {{ plan.cta }}
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  setup() {
    const plans = [
      {
        name: 'Listener',
        price: '$0',
        features: [
          '15-minute check-in call',
          'One issue or question',
          'Tips for next steps',
          'Available 1x per patient',
        ],
        cta: 'Start Here',
        featured: false,
      },
      {
        name: 'Companion',
        price: '$120/wk',
        features: [
          '1-hour weekly support',
          'Appointment preparation',
          'Post-visit review',
          'Phone/email follow-up',
        ],
        cta: 'Get Support',
        featured: false,
      },
      {
        name: 'Advocate',
        price: '$240/wk',
        features: [
          '2 hours of advocacy',
          'In-person or virtual visit support',
          'Medical note translation',
          'Care coordination assistance',
        ],
        cta: 'Book Advocate',
        featured: true,
      },
      {
        name: 'Family Circle',
        price: '$480/wk',
        features: [
          '4 hours support per week',
          'Multiple appointments',
          'Ongoing care planning',
          'Full family updates & guidance',
        ],
        cta: 'Build a Plan',
        featured: false,
      },
    ];

    return { plans };
  },
};
</script>
