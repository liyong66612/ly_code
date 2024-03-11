<script lang="ts" setup>
import { ref } from "vue"

const datevalue = ref({})
const radio = ref({})
</script>
<template>
  <div class="page-wrapper">
    <div class="page-header d-print-none">
      <div class="container-xl">
        <div class="row g-2 align-items-center">
          <div class="col">
            <!-- Page pre-title -->
            <h2 class="page-title">全部访客名单</h2>
          </div>
          <!-- Page title actions -->
          <div class="col-auto ms-auto d-print-none">
            <div class="btn-list">
              <span class="d-none d-sm-inline">
                <a href="#" class="btn"> New view </a>
              </span>
              <a
                href="#"
                class="btn btn-primary d-none d-sm-inline-block"
                data-bs-toggle="modal"
                data-bs-target="#modal-report"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="icon"
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  stroke-width="2"
                  stroke="currentColor"
                  fill="none"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                  <path d="M12 5l0 14" />
                  <path d="M5 12l14 0" />
                </svg>
                Create new report
              </a>
              <a
                href="#"
                class="btn btn-primary d-sm-none btn-icon"
                data-bs-toggle="modal"
                data-bs-target="#modal-report"
                aria-label="Create new report"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="icon"
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  stroke-width="2"
                  stroke="currentColor"
                  fill="none"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                  <path d="M12 5l0 14" />
                  <path d="M5 12l14 0" />
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="page-body">
      <div class="container-xl">
        <div class="row row-deck row-cards">
          <div class="col-lg-6">
            <div class="row row-cards">
              <div class="col-12">
                <div class="row g-2 align-items-center">
                  <div class="col">
                    <el-date-picker
                      v-model="datevalue"
                      type="daterange"
                      range-separator="~"
                      start-placeholder="Start date"
                      end-placeholder="End date"
                    />
                  </div>
                  <div class="col-auto ms-auto d-print-none">
                    <el-radio-group v-model="radio">
                      <el-radio :value="3">全部</el-radio>
                      <el-radio :value="6">已到访</el-radio>
                      <el-radio :value="9">未到访</el-radio>
                    </el-radio-group>
                  </div>
                </div>
              </div>
              <!-- <div class="col-12">
                <div class="card" style="height: 28rem">
                  <div class="card-body card-body-scrollable card-body-scrollable-shadow">
                    <div class="divide-y">
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar">JL</span>
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Jeffie Lewzey</strong> commented on your <strong>"I'm not a witch."</strong> post.
                            </div>
                            <div class="text-secondary">yesterday</div>
                          </div>
                          <div class="col-auto align-self-center">
                            <div class="badge bg-primary" />
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/002m.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              It's <strong>Mallory Hulme</strong>'s birthday. Wish him well!
                            </div>
                            <div class="text-secondary">2 days ago</div>
                          </div>
                          <div class="col-auto align-self-center">
                            <div class="badge bg-primary" />
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/003m.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Dunn Slane</strong> posted <strong>"Well, what do you want?"</strong>.
                            </div>
                            <div class="text-secondary">today</div>
                          </div>
                          <div class="col-auto align-self-center">
                            <div class="badge bg-primary" />
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/000f.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Emmy Levet</strong> created a new project <strong>Morning alarm clock</strong>.
                            </div>
                            <div class="text-secondary">4 days ago</div>
                          </div>
                          <div class="col-auto align-self-center">
                            <div class="badge bg-primary" />
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/001f.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate"><strong>Maryjo Lebarree</strong> liked your photo.</div>
                            <div class="text-secondary">2 days ago</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar">EP</span>
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Egan Poetz</strong> registered new client as <strong>Trilia</strong>.
                            </div>
                            <div class="text-secondary">yesterday</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/002f.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Kellie Skingley</strong> closed a new deal on project
                              <strong>Pen Pineapple Apple Pen</strong>.
                            </div>
                            <div class="text-secondary">2 days ago</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/003f.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Christabel Charlwood</strong> created a new project for <strong>Wikibox</strong>.
                            </div>
                            <div class="text-secondary">4 days ago</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar">HS</span>
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Haskel Shelper</strong> change status of <strong>Tabler Icons</strong> from
                              <strong>open</strong> to <strong>closed</strong>.
                            </div>
                            <div class="text-secondary">today</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/006m.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Lorry Mion</strong> liked <strong>Tabler UI Kit</strong>.
                            </div>
                            <div class="text-secondary">yesterday</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/004f.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate"><strong>Leesa Beaty</strong> posted new video.</div>
                            <div class="text-secondary">2 days ago</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/007m.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate"><strong>Perren Keemar</strong> and 3 others followed you.</div>
                            <div class="text-secondary">2 days ago</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar">SA</span>
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Sunny Airey</strong> upload 3 new photos to category
                              <strong>Inspirations</strong>.
                            </div>
                            <div class="text-secondary">2 days ago</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/009m.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Geoffry Flaunders</strong> made a <strong>$10</strong> donation.
                            </div>
                            <div class="text-secondary">2 days ago</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/010m.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate"><strong>Thatcher Keel</strong> created a profile.</div>
                            <div class="text-secondary">3 days ago</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/005f.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Dyann Escala</strong> hosted the event <strong>Tabler UI Birthday</strong>.
                            </div>
                            <div class="text-secondary">4 days ago</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar" style="background-image: url(./static/avatars/006f.jpg)" />
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Avivah Mugleston</strong> mentioned you on <strong>Best of 2020</strong>.
                            </div>
                            <div class="text-secondary">2 days ago</div>
                          </div>
                        </div>
                      </div>
                      <div>
                        <div class="row">
                          <div class="col-auto">
                            <span class="avatar">AA</span>
                          </div>
                          <div class="col">
                            <div class="text-truncate">
                              <strong>Arlie Armstead</strong> sent a Review Request to <strong>Amanda Blake</strong>.
                            </div>
                            <div class="text-secondary">2 days ago</div>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div> -->
            </div>
          </div>
          <div class="col-12">
            <div class="row row-cards">
              <div class="col-sm-6 col-lg-3">
                <div class="card card-sm">
                  <div class="card-body">
                    <div class="row align-items-center">
                      <div class="col">
                        <div class="h2 mb-0">XXX</div>
                        <div class="font-weight-medium">预约时间: 2024/3/6 14:30</div>
                        <div class="text-secondary">状态: 未到访</div>
                      </div>
                      <div class="col-auto">
                        <span class="bg-primary text-white avatar"
                          ><!-- Download SVG icon from http://tabler-icons.io/i/currency-dollar -->
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="icon"
                            width="24"
                            height="24"
                            viewBox="0 0 24 24"
                            stroke-width="2"
                            stroke="currentColor"
                            fill="none"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                          >
                            <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                            <path d="M16.7 8a3 3 0 0 0 -2.7 -2h-4a3 3 0 0 0 0 6h4a3 3 0 0 1 0 6h-4a3 3 0 0 1 -2.7 -2" />
                            <path d="M12 3v3m0 12v3" />
                          </svg>
                        </span>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="col-sm-6 col-lg-3">
                <router-link to="/userinfo/detail">
                  <div class="card card-sm">
                    <div class="card-body">
                      <div class="row align-items-center">
                        <div class="col">
                          <div class="h2 mb-0">XXX</div>
                          <div class="font-weight-medium">预约时间: 2024/3/6 14:30</div>
                          <div class="text-secondary">状态: 未到访</div>
                        </div>
                        <div class="col-auto">
                          <span class="bg-primary text-white avatar"
                            ><!-- Download SVG icon from http://tabler-icons.io/i/currency-dollar -->
                            <svg
                              xmlns="http://www.w3.org/2000/svg"
                              class="icon"
                              width="24"
                              height="24"
                              viewBox="0 0 24 24"
                              stroke-width="2"
                              stroke="currentColor"
                              fill="none"
                              stroke-linecap="round"
                              stroke-linejoin="round"
                            >
                              <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                              <path
                                d="M16.7 8a3 3 0 0 0 -2.7 -2h-4a3 3 0 0 0 0 6h4a3 3 0 0 1 0 6h-4a3 3 0 0 1 -2.7 -2"
                              />
                              <path d="M12 3v3m0 12v3" />
                            </svg>
                          </span>
                        </div>
                      </div>
                    </div>
                  </div>
                </router-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- 弹出层 -->
    <div class="modal modal-blur fade" id="modal-report" tabindex="-1" role="dialog" aria-hidden="true">
      <div class="modal-dialog modal-lg" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">New report</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close" />
          </div>
          <div class="modal-body">
            <div class="mb-3">
              <label class="form-label">Name</label>
              <input type="text" class="form-control" name="example-text-input" placeholder="Your report name" />
            </div>
            <label class="form-label">Report type</label>
            <div class="form-selectgroup-boxes row mb-3">
              <div class="col-lg-6">
                <label class="form-selectgroup-item">
                  <input type="radio" name="report-type" value="1" class="form-selectgroup-input" checked />
                  <span class="form-selectgroup-label d-flex align-items-center p-3">
                    <span class="me-3">
                      <span class="form-selectgroup-check" />
                    </span>
                    <span class="form-selectgroup-label-content">
                      <span class="form-selectgroup-title strong mb-1">Simple</span>
                      <span class="d-block text-secondary">Provide only basic data needed for the report</span>
                    </span>
                  </span>
                </label>
              </div>
              <div class="col-lg-6">
                <label class="form-selectgroup-item">
                  <input type="radio" name="report-type" value="1" class="form-selectgroup-input" />
                  <span class="form-selectgroup-label d-flex align-items-center p-3">
                    <span class="me-3">
                      <span class="form-selectgroup-check" />
                    </span>
                    <span class="form-selectgroup-label-content">
                      <span class="form-selectgroup-title strong mb-1">Advanced</span>
                      <span class="d-block text-secondary"
                        >Insert charts and additional advanced analyses to be inserted in the report</span
                      >
                    </span>
                  </span>
                </label>
              </div>
            </div>
            <div class="row">
              <div class="col-lg-8">
                <div class="mb-3">
                  <label class="form-label">Report url</label>
                  <div class="input-group input-group-flat">
                    <span class="input-group-text"> https://tabler.io/reports/ </span>
                    <input type="text" class="form-control ps-0" value="report-01" autocomplete="off" />
                  </div>
                </div>
              </div>
              <div class="col-lg-4">
                <div class="mb-3">
                  <label class="form-label">Visibility</label>
                  <select class="form-select">
                    <option value="1" selected>Private</option>
                    <option value="2">Public</option>
                    <option value="3">Hidden</option>
                  </select>
                </div>
              </div>
            </div>
          </div>
          <div class="modal-footer">
            <a href="#" class="btn btn-link link-secondary" data-bs-dismiss="modal"> Cancel </a>
            <a href="#" class="btn btn-primary ms-auto" data-bs-dismiss="modal">
              <!-- Download SVG icon from http://tabler-icons.io/i/plus -->
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="icon"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                stroke-width="2"
                stroke="currentColor"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                <path d="M12 5l0 14" />
                <path d="M5 12l14 0" />
              </svg>
              Create new report
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.dropdown-toggle:after {
  border-top: none;
  border-right: none;
}
.el-radio {
  margin-right: 0.5rem !important;
}
</style>
