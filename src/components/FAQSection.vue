<template>
    <section class="faq-section">
        <div class="container">
            <p class="faq-label">FAQ</p>
            <h2 class="faq-title">Get all your questions answered here</h2>

            <div class="faq-list">
                <div v-for="(faq, index) in faqs" :key="index" class="faq-item">
                    <button class="faq-header" @click="toggleFAQ(index)">
                        <span class="faq-question">{{ faq.question }}</span>
                        <span class="faq-toggle" :class="{ open: faq.open }">
                            {{ faq.open ? '−' : '+' }}
                        </span> </button>

                    <div class="faq-answer" v-show="faq.open">
                        <p>{{ faq.answer }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            faqs: [
                { question: "Get all your questions answered here", answer: "Yes, absolutely. You do not need to be a 500 hour yoga TTC trained expert to become a best yoga teacher in Rishikesh. Moreover, you do not need to do headstands and Hanuman Asana, to be considered competent. You will be amazed to know that many people go for yoga teacher training at first, to deepen their knowledge. Amongst the beginner level learners, many get ample time to practice and perfect their yoga poses. The 200 hour yoga TTC is the perfect stepping stone for you to embrace the idea of teaching. You can always take up a job as assistant yoga teacher, after completing the training.", open: false },
                { question: "What Type Of Yoga Will You Teach?", answer: "Join a global community of yoga instructors, access career guidance, and explore teaching opportunities worldwide.", open: false },
                { question: "What Is Yoga Alliance Certification?", answer: "Empower yourself to teach yoga anywhere or build your own yoga retreat with the business knowledge we provide.", open: false },
                { question: "Airport Pick Up is available?", answer: "Empower yourself to teach yoga anywhere or build your own yoga retreat with the business knowledge we provide.", open: false }
            ]
        };
    },
    methods: {
        toggleFAQ(index) {
            this.faqs = this.faqs.map((faq, i) =>
                i === index ? { ...faq, open: !faq.open } : { ...faq, open: false }
            );
        }
    }
};
</script>

<style scoped>
.faq-section {
    padding: 48px 24px;
    text-align: left;
}

.faq-label {
    color: #ff6600;
    font-size: 14px;
    font-weight: 400;
    text-transform: uppercase;
    margin-bottom: 8px;
}

.faq-title {
    font-size: 28px;
    color: #734875;
    font-weight: 400;
    margin-bottom: 24px;
}

.faq-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.faq-item {
    background: #fdf3f0;
    border-radius: 12px;
    padding: 16px;
    transition: all 0.3s ease-in-out;
}

.faq-header {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    text-align: start;
    font-size: 16px;
    font-weight: 500;
    color: #482c5a;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0;
    letter-spacing: 0;
}

.faq-toggle {
    display: inline-flex;
    justify-content: center;
    align-items: center;
    width: 28px;
    height: 28px;
    border-radius: 6px;
    background: #fde8e4;
    color: #734875;
    font-size: 18px;
    font-weight: bold;
    letter-spacing: 0;
    transition: transform 0.3s ease-in-out;
}



.faq-answer {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.4s ease-in-out, opacity 0.3s ease-in-out;
    opacity: 0;
    padding: 0 16px;
}

.faq-answer p {
    font-size: 14px;
    font-family: 400;
    letter-spacing: 0;
}

.faq-question{
    letter-spacing: 0;
}

.faq-item .faq-answer {
    max-height: 300px;
    opacity: 1;
    transition: max-height 0.4s ease-in-out, opacity 0.3s ease-in-out;
}

.faq-list {
    overflow: hidden;
    scroll-behavior: smooth;
}
</style>