<template>
  <div class="slider-container">
    <div class="slider-header">
      <span>Xem tất cả</span>
      <span class="arrow">&#8250;</span>
    </div>
    <div class="slider">
      <button class="nav-btn left">&#171;</button>
      <div class="card-list">
        <div v-for="(card, i) in cards" :key="i" class="card">
          <div class="card-img">
            <img :src="card.img" alt="card" />
            <span v-if="card.hot" class="hot-badge">HOT</span>
          </div>
          <div class="card-info">
            <div class="card-title">
              <img v-if="card.icon" :src="card.icon" class="icon" />
              <span v-if="card.type==='match'">Team A <span class="vs">vs</span> Team B</span>
              <span v-else>Team A <span class="vs">vs</span> Team B</span>
            </div>
            <div class="card-caster">BLV NONAME</div>
          </div>
          <div class="card-footer">
            <button v-if="card.status==='live'" class="live-btn">LIVE</button>
            <button v-else-if="card.status==='cancel'" class="cancel-btn">Huỷ lịch</button>
            <button v-else class="schedule-btn">
              <span class="bell">&#128276;</span> Đặt lịch
            </button>
          </div>
        </div>
      </div>
      <button class="nav-btn right">&#187;</button>
    </div>
  </div>
</template>

<script setup>
const cards = [
  {
    img: 'https://images.unsplash.com/photo-1517649763962-0c623066013b?auto=format&fit=crop&w=400&q=80',
    hot: true,
    type: 'match',
    icon: 'https://cdn-icons-png.flaticon.com/512/69/69524.png',
    status: 'live',
  },
  {
    img: 'https://images.unsplash.com/photo-1464983953574-0892a716854b?auto=format&fit=crop&w=400&q=80',
    hot: true,
    type: 'game',
    icon: 'https://cdn-icons-png.flaticon.com/512/833/833314.png',
    status: 'cancel',
  },
  {
    img: 'https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=400&q=80',
    hot: false,
    type: 'match',
    icon: 'https://cdn-icons-png.flaticon.com/512/69/69524.png',
    status: 'schedule',
  },
  {
    img: 'https://images.unsplash.com/photo-1517649763962-0c623066013b?auto=format&fit=crop&w=400&q=80',
    hot: false,
    type: 'match',
    icon: 'https://cdn-icons-png.flaticon.com/512/69/69524.png',
    status: 'schedule',
  },
  {
    img: 'https://images.unsplash.com/photo-1464983953574-0892a716854b?auto=format&fit=crop&w=400&q=80',
    hot: false,
    type: 'game',
    icon: 'https://cdn-icons-png.flaticon.com/512/833/833314.png',
    status: 'schedule',
  },
  {
    img: 'https://images.unsplash.com/photo-1464983953574-0892a716854b?auto=format&fit=crop&w=400&q=80',
    hot: false,
    type: 'game',
    icon: 'https://cdn-icons-png.flaticon.com/512/833/833314.png',
    status: 'schedule',
  },
  {
    img: 'https://images.unsplash.com/photo-1464983953574-0892a716854b?auto=format&fit=crop&w=400&q=80',
    hot: false,
    type: 'game',
    icon: 'https://cdn-icons-png.flaticon.com/512/833/833314.png',
    status: 'schedule',
  },
  {
    img: 'https://images.unsplash.com/photo-1464983953574-0892a716854b?auto=format&fit=crop&w=400&q=80',
    hot: false,
    type: 'game',
    icon: 'https://cdn-icons-png.flaticon.com/512/833/833314.png',
    status: 'schedule',
  },
];
</script>

<style scoped>
.slider-container {
  background: #f3f3f5;
  border-radius: 12px;
  padding: 18px 0 0 0;
  margin: 24px;
  position: relative;
}
.slider-header {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  font-size: 15px;
  color: #222;
  padding: 0 24px 8px 0;
  font-weight: 500;
  gap: 4px;
}
.slider-header .arrow {
  font-size: 18px;
  margin-left: 2px;
}
.slider {
  display: flex;
  align-items: center;
  position: relative;
}
.card-list {
  display: flex;
  gap: 18px;
  overflow-x: auto;
  padding: 0 8px;
  scroll-behavior: smooth;
}
.card {
  min-width: 220px;
  max-width: 240px;
  background: #fff;
  border-radius: 16px;
  box-shadow: 0 2px 8px #0001;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  margin-bottom: 8px;
  position: relative;
}
.card-img {
  position: relative;
  height: 100px;
  overflow: hidden;
}
.card-img img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.hot-badge {
  position: absolute;
  top: 8px;
  right: 8px;
  background: #ff3c3c;
  color: #fff;
  font-weight: bold;
  font-size: 12px;
  padding: 2px 8px;
  border-radius: 10px;
  box-shadow: 0 1px 4px #0002;
  letter-spacing: 1px;
}
.card-info {
  background: linear-gradient(0deg, #ffe082 80%, #fff0 100%);
  padding: 10px 10px 0 10px;
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.card-title {
  font-size: 15px;
  font-weight: 600;
  color: #222;
  display: flex;
  align-items: center;
  gap: 5px;
}
.card-title .icon {
  width: 18px;
  height: 18px;
  margin-right: 4px;
}
.card-title .vs {
  color: #ffb300;
  font-weight: bold;
  margin: 0 3px;
}
.card-caster {
  font-size: 14px;
  color: #222;
  font-weight: 700;
  margin-top: 2px;
  letter-spacing: 1px;
}
.card-footer {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 8px 10px 10px 10px;
  gap: 6px;
}
.live-btn {
  background: #ff3c3c;
  color: #fff;
  border: none;
  border-radius: 8px;
  padding: 4px 14px;
  font-weight: bold;
  font-size: 13px;
  box-shadow: 0 1px 4px #0002;
}
.cancel-btn {
  background: #e0e0e0;
  color: #222;
  border: none;
  border-radius: 8px;
  padding: 4px 14px;
  font-weight: bold;
  font-size: 13px;
}
.schedule-btn {
  background: linear-gradient(90deg, #ffe082 0%, #ffd54f 100%);
  color: #222;
  border: none;
  border-radius: 8px;
  padding: 4px 14px;
  font-weight: bold;
  font-size: 13px;
  display: flex;
  align-items: center;
  gap: 4px;
  box-shadow: 0 1px 4px #0001;
}
.bell {
  font-size: 15px;
}
.nav-btn {
  background: #fff;
  border: none;
  border-radius: 50%;
  width: 32px;
  height: 64px;
  font-size: 22px;
  color: #888;
  box-shadow: 0 2px 8px #0001;
  cursor: pointer;
  z-index: 2;
  transition: background 0.2s;
  position: relative;
}
.nav-btn.left {
  margin-right: -12px;
}
.nav-btn.right {
  margin-left: -12px;
}
.nav-btn:hover {
  background: #ffe082;
}
</style>