<!-- This is the OurServices.vue component -->
<template>
    <div class="pt-2 pb-24 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="mt-10">
          <h2 class="text-3xl text-center font-bold pb-12">Our Services</h2>
          <dl class="space-y-10 md:space-y-0 md:grid md:grid-cols-1 md:gap-x-8 md:gap-y-10">
            <div v-for="feature in features" :key="feature.name" class="relative ml-20" >
              <dt>
                <div class="absolute flex items-center justify-center h-12 w-12 rounded-full bg-pink-500 text-white" >
                  <component :is="feature.icon" class="h-6 w-6" aria-hidden="true" />
                </div>
                <p class="ml-16 text-lg leading-6 font-medium text-gray-900">
                  {{ feature.name }}
                </p>
              </dt>
              <dd class="mt-2 ml-16 text-base text-gray-500">
                {{ feature.description }}
              </dd>
            </div>
          </dl>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import {
    GlobeAltIcon,
    AnnotationIcon,
    LightningBoltIcon,
    CodeIcon,
    ScaleIcon,
    ChartBarIcon,
  } from '@heroicons/vue/outline'
  
  
  const features = [
    {
      name: 'Patient Advocacy During Appointments',
      description:
        'Trained advocates accompany elderly patients to medical visits to ensure concerns are heard, questions are answered, and care decisions are fully understood.',
      icon: GlobeAltIcon,
    },
    {
      name: 'Pre-Visit Preparation',
      description:
        'We help patients and families prepare for upcoming health visits by organizing questions, reviewing medications, and identifying key concerns to discuss with providers.',
      icon: AnnotationIcon,
    },
    {
      name: 'Follow-Up & Care Coordination',
      description:
        'After the appointment, we provide support by reviewing care plans, clarifying next steps, and helping patients follow through with treatments, referrals, or changes.',
      icon: LightningBoltIcon,
    },
    {
      name: 'Cognitive & Emotional Support',
      description:
        'Our team offers compassionate, trauma-informed support to patients who may feel overwhelmed, confused, or unheard—ensuring they are treated with dignity and patience.',
      icon: CodeIcon,
    },
    {
      name: 'Provider Partnership Programs',
      description:
        'We work with clinics, hospitals, and long-term care providers to train staff on communication best practices and implement patient-centered care initiatives.',
      icon: ScaleIcon,
    },
    
  ]
  
  export default {
  setup() {
    return {
      features
    }
  }
}
  </script>
  